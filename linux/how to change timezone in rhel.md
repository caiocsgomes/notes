# How to change timezone in rhel

`timedatectl` is the command that manages system time and date.

To list the timezones:

```bash
timedatectl list-timezones
```

To set one of the available timezones:

```bash
timedatectl set-timezone ZONE

# example
timedatectl set-timezone Asia/Kabul
```

