
# yum

## configure local repo

Create the repo
```bash
createrepo /var/www/html/myrepo
```

Configure the config file (`/etc/yum.repos.d/myrepo.repo`)

```txt
[myrepo]
name=My Repository
baseurl=file:///var/www/html/myrepo/
enabled=1
gpgcheck=0
```

Clean, list and install form local repo
```bash
yum clean all
yum repolist
yum --enablerepo=REPO_NAME install PACKAGE_NAME
```