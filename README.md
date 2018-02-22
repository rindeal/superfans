# superfans
Tools for managing fans on Supermicro chassis via IPMI.
```
Usage: superfans [OPTIONS] COMMAND [ARGS]...

  Tools for managing fans on a Supermicro chassis.

  Fan presets can be adjusted, or fans manually updated to a certain speed.

  If a hostname is specified, superfans will use the specified username and
  password to connect. If a hostname is not specified, ipmitool will talk to
  the local machine using the IPMI kernel module.

  When setting fan speed manually, the fan preset must be set to Full, or
  else the hardware fan controller will automatically adjust the speed again
  after some time has passed.

  For a list of presets, use `superfans preset --help`.

  If needed, the hostname, username, and password options should precede
  commands. A hostname of "localhost" will skip IPMI over lanplus and use
  the kernel module instead.

  Example:
  ./superfans -h bigbertha -u monkey -p secrets preset full

Options:
  -h, --hostname TEXT  Remote hostname (default: local)
  -u, --username TEXT  Remote IPMI username
  -p, --password TEXT  Remote IPMI password
  -e, --env-password   Use IPMI_PASSWORD environment variable for password
  --help               Show this message and exit.

Commands:
  preset  Applies a factory preset to fan controller.
  set     Set fan speed to a fixed %.
  status  Retrieves fan controller preset & fan speed.
```

