# IPTABLES to Oracle Cloud port 80 and 443 open

If you need to open up ports  `80`  and  `443`, on file `/etc/iptables/rules.v4` just add

```bash
-A INPUT -p tcp -m state --state NEW -m multiport --dports 80,443 -j ACCEPT
```

directly below

```bash
-A INPUT -p tcp -m state --state NEW -m tcp --dport 22 -j ACCEPT
```

And reboot OR run bellow

```bash
sudo /sbin/iptables-restore < /etc/iptables/rules.v4
```

Thanks for the suggestion [@11k](https://gist.github.com/mrladeia/da43fc783610758c6dbcaba22b4f7acd?permalink_comment_id=4183429#gistcomment-4183429)

# Another way

See that some lines of the `rules.v4` file are commented with # at the beginning
