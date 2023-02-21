
# How to redirect in apache

The `/etc/httpd/conf/httpd.conf` file is the apache configuration file, to make redirections we append to this file. 

For example, to redirect from non www to www:

```xml
<VirtualHost *:8087>
    ServerName stapp02.stratos.xfusioncorp.com
    Redirect 301 / http://www.stapp02.stratos.xfusioncorp.com:8087/
</VirtualHost>
```

301 means permanent redirect. 

Then to redirect from /blog to /news for example:

```xml
<VirtualHost *:8087>
    ServerName www.stapp02.stratos.xfusioncorp.com
    Redirect 302 /blog http://www.stapp02.stratos.xfusioncorp.com:8087/news
</VirtualHost>
```

302 means temporary.

After this remember to restart the service.