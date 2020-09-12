# heartbeat



This chart deploys heartbeat agents to all the nodes in your cluster via a DaemonSet.

By default this chart only ships a single output to a file on the local system.  Users should set config.output.file.enabled=false and configure their own outputs as [documented](https://www.elastic.co/guide/en/beats/heartbeat/current/configuring-output.html)


## Configuration

The following table lists the configurable parameters of the heartbeat chart and their default values.

| Parameter                           | Description                                                                                                                                                                                           | Default                             |
| ----------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------- |
| `image.repository`                  | The image repository to pull from                                                                                                                                                                     | `docker.elastic.co/beats/heartbeat` |
| `image.tag`                         | The image tag to pull                                                                                                                                                                                 | `6.7.0`                             |
| `image.pullPolicy`                  | Image pull policy                                                                                                                                                                                     | `IfNotPresent`                      |
| `rbac.create`                       | If true, create & use RBAC resources                                                                                                                                                                  | `true`                              |
| `rbac.serviceAccount`               | existing ServiceAccount to use (ignored if rbac.create=true)                                                                                                                                          | `default`                           |
| `config`                            | The content of the configuration file consumed by heartbeat. See the [heartbeat documentation](https://www.elastic.co/guide/en/beats/heartbeat/current/heartbeat-reference-yml.html) for full details |                               |
| `plugins`                           | List of beat plugins                                                                                                                                                                                  |                                     |
| `hostNetwork`                       | If true, use hostNetwork                                                                                                                                                                              | `false`                             |
| `extraVars`                         | A map of additional environment variables                                                                                                                                                             |                                     |
| `extraVolumes`, `extraVolumeMounts` | Additional volumes and mounts, for example to provide other configuration files                                                                                                                       |                                     |
| `resources.requests.cpu`            | CPU resource requests                                                                                                                                                                                 |                                     |
| `resources.limits.cpu`              | CPU resource limits                                                                                                                                                                                   |                                     |
| `resources.requests.memory`         | Memory resource requests                                                                                                                                                                              |                                     |
| `resources.limits.memory`           | Memory resource limits                                                                                                                                                                                |                                     |
| `priorityClassName`                 | Priority class name                                                                                                                                                                                   |                                     |
| `nodeSelector`                      | Node Selector                                                                                                                                                                                         |                                     |
| `tolerations`                       | Pod's tolerations                                                                                                                                                                                     |                                     |

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`. For example,

```bash
$ helm install --name my-release \
    --set rbac.create=true \
    stable/heartbeat
```

Alternatively, a YAML file that specifies the values for the parameters can be provided while installing the chart. For example,

```bash
$ helm install --name my-release -f values.yaml stable/heartbeat
```

