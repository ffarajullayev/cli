# CLI getting started

To install the CLI visit the <https://github.com/azintelecom/cli/releases> and find the latest release for your system.

After downloading the CLI, make sure it is available in your ```PATH``` environment variable. It will simplify all the further actions.

## Verify the installation

To verify your installation, run:

```shell
azin
```

You should see the output similar to this:

```shell
azin, command line interface to manage AzCloud

Usage:
  azin [command]

Available Commands:
  docs        Show "azin" utility documentation
  help        Help about any command
  net         Manage AzCloud networks
  quota       View AzCloud quota
  task        Manage AzCloud tasks
  user        AzCloud user management
  vm          Manage AzCloud instances

Flags:
  -h, --help              help for azin
  -l, --loglevel string   Set loglevel (default "debug")
  -o, --output string     Output [table,json] (default "table")

Use "azin [command] --help" for more information about a command.
```