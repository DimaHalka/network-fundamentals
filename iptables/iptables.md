```

sudo iptables -A INPUT -i lo -p tcp --dport 10000 -j ACCEPT 
sudo iptables -A INPUT       -p tcp --dport 10000 -j DROP

```
