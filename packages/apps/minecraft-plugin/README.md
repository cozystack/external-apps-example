# minecraft-plugin

Managed Minecraft plugin installation powered by [minecraft-operator](https://github.com/lexfrei/minecraft-operator).

## Parameters

### Plugin source

| Name         | Description                                                                                             | Type     | Value    |
| ------------ | ------------------------------------------------------------------------------------------------------- | -------- | -------- |
| `sourceType` | Plugin source type.                                                                                     | `string` | `hangar` |
| `project`    | Plugin project identifier on Hangar (e.g. BlueMap). The operator requires it when sourceType is hangar. | `string` | `""`     |
| `url`        | Direct download URL of the plugin JAR. The operator requires it when sourceType is url.                 | `string` | `""`     |
| `checksum`   | Optional SHA-256 checksum (64 hex characters) of the JAR file, used with sourceType url.                | `string` | `""`     |


### Version management

| Name             | Description                                                                           | Type     | Value    |
| ---------------- | ------------------------------------------------------------------------------------- | -------- | -------- |
| `updateStrategy` | Update strategy for the plugin version.                                               | `string` | `latest` |
| `version`        | Target plugin version. The operator requires it for the pin and build-pin strategies. | `string` | `""`     |


### Server binding

| Name                           | Description                                                                                                                                           | Type                | Value |
| ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----- |
| `instanceSelector`             | Selector for the servers this plugin is installed on. The label value to match is the Helm release name of the server app, `minecraft-server-<name>`. | `object`            | `{}`  |
| `instanceSelector.matchLabels` | Labels a PaperMCServer must carry to be selected. An empty selector matches every server in the namespace.                                            | `map[string]string` | `{}`  |


### Network endpoints

| Name                    | Description                               | Type       | Value |
| ----------------------- | ----------------------------------------- | ---------- | ----- |
| `endpoints`             | Network endpoints exposed by this plugin. | `[]object` | `[]`  |
| `endpoints[i].name`     | Endpoint name (DNS label).                | `string`   | `""`  |
| `endpoints[i].port`     | Port number.                              | `int`      | `0`   |
| `endpoints[i].protocol` | Endpoint protocol.                        | `string`   | `TCP` |

