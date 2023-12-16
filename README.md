# Ansible Role: VSCode

> An Ansible Role that installs and configures [Visual Studio Code](https://code.visualstudio.com/) on MacOS.

## Variables

The `vscode_extensions` variable can be used to install and remove vscode extensions - tasks will be skipped if the variable is set to `null` (defaults: `null`).

**Important!** Ansible will remove every extension that is not listed under `vscode_extensions`.

```yaml
vscode_extensions:
- ms-azuretools.vscode-docker
- MS-CEINTL.vscode-language-pack-de
```

The `vscode_settings` is a yaml-dictionary which is converted to json and is used to manage your vscode configuration (`settings.json`). For satey the boolean variable `vscode_settings_backup` can be set to `true` (defaults: `false`) to create a backup, before ansible will change up the configuration. The Configuration-Tasks will be skipped, if the variable is set to `null` (defaults: `null`).

```yaml
vscode_settings_backup: true
vscode_settings:
  files.autoSave: afterDelay
  files.insertFinalNewline: true
  window.zoomLevel: 1
  workbench.startupEditor: none
```

## Example

The following Playbook will only install vscode and setup a basic configuration.

```yaml
- hosts: all
  roles:
  - dudecalledbro.vscode
```

## License

Copyright © 2023 Niclas Spreng

Licensed under the [MIT license](LICENSE).
