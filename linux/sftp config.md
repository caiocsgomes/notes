# sftp config

To configure sftp the sshd deamon has to be running and with the config (`/etc/ssh/sshd_config`) below added. Don't forget to remove the current `sftp` config.

```bash
Subsystem   sftp    internal-sftp -d /webapp
Match Group USER_GROUP
ChrootDirectory /var/www
AllowTCPForwarding no
X11Forwarding no
ForceCommand internal-sftp 
```

The `/webapp` has to belong to the USER_GROUP from the user that is accesing the `sftp` server and `/var/www`, which is the folder where `webapp` lives, has to belong to `root:root`.  The confir will allow sftp and block ssh.

- https://askubuntu.com/questions/950979/setup-sftp-user-account-and-restric-read-write-access-to-one-folder
- https://serverfault.com/questions/539261/allow-sftp-and-process-running-but-disallow-ssh-for-a-single-user