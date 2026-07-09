# minecraft-server

Managed PaperMC Minecraft server powered by [minecraft-operator](https://github.com/lexfrei/minecraft-operator).

## Parameters

### Server configuration

| Name             | Description                                                                              | Type       | Value    |
| ---------------- | ---------------------------------------------------------------------------------------- | ---------- | -------- |
| `updateStrategy` | Update strategy for the Paper server version.                                            | `string`   | `latest` |
| `version`        | Target Minecraft version. The operator requires it for the pin and build-pin strategies. | `string`   | `""`     |
| `memoryLimit`    | Memory limit for the server container.                                                   | `quantity` | `2Gi`    |
| `cpuLimit`       | CPU limit for the server container.                                                      | `quantity` | `2000m`  |


### Service configuration

| Name          | Description                             | Type     | Value          |
| ------------- | --------------------------------------- | -------- | -------------- |
| `serviceType` | Service type used to expose the server. | `string` | `LoadBalancer` |


### Backup configuration

| Name              | Description                                 | Type     | Value         |
| ----------------- | ------------------------------------------- | -------- | ------------- |
| `backupEnabled`   | Enable VolumeSnapshot-based backups.        | `bool`   | `false`       |
| `backupSchedule`  | Cron schedule for periodic backups.         | `string` | `0 */6 * * *` |
| `backupRetention` | Maximum number of backup snapshots to keep. | `int`    | `10`          |


### Update schedule

| Name        | Description                                   | Type     | Value         |
| ----------- | --------------------------------------------- | -------- | ------------- |
| `checkCron` | Cron schedule for checking for Paper updates. | `string` | `0 */4 * * *` |

