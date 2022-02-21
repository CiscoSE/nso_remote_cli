# NSO Remote CLI

Simple CLI utility to manage NSO remotely from the command line.

Credentials can be set using the following environmental variables

```bash
NSO_RESTCONF_URL 
NSO_USER 
NSO_PASSWORD
```

## Supported subcommands

### Add devices usage

```bash
% ./nso_remote_cli add-devices --help
Usage: nso_remote_cli add-devices [OPTIONS]

  Add devices into NSO

Options:
  -i, --inventory-file TEXT      NSO Inventory file in yaml format. Use
                                 --print-inventory-example to generate one
                                 [default: ./nso_device_inventory.yaml]
  -e, --print-inventory-example  Print example inventory file
  --help                         Show this message and exit.
```

Parameters can be added to the inventory file as needed, as long as they are defined in the yang models. If you are 
not sure how to add your devices with extra settings, add one device manually in NSO, 
execute "show running-config devices device <name> | de-select config | display json" and convert the output to yaml

#### Example output

```bash
% ./nso_remote_cli add-devices -i test.yaml
Devices added successfully
```

## Install

1. It is strongly recommended to use virtual environments
2. Install dependencies in requirements.txt
3. Test using nso_remote_cli --help

```bash
% ./nso_remote_cli --help            
Usage: nso_remote_cli [OPTIONS] COMMAND [ARGS]...

  Top level command

Options:
  --help  Show this message and exit.

Commands:
  add-devices  Add devices into NSO
```

## Authors

* Santiago Flores Kanter (sfloresk@cisco.com)
