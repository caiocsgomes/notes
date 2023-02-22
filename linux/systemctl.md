# systemctl

List all running services
```sh
systemctl
```

Start a service
```sh
systemctl start SERVICE
```

Enable (make the service start at boot) a service
```sh
systemctl enable SERVICE
```

List all unit files. A unit is any service the systemd know how to operate.
```sh
systemctl list-unit-files
```