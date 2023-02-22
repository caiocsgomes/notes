# How to block all incoming traffic to a port in linux with iptables


```sh
sudo iptables -A INPUT -p tcp --dport 5003 -j DROP

sudo iptables -A INPUT -p tcp --dport 8095 -j ACCEPT

service iptables save
```