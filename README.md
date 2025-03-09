# 作業手順書

## インストール

* ports で security/py-certbot-dns-powerdns を入れる

```
# sudo sh
# portsnap fetch update
# cd /usr/ports/py-certbot-dns-powerdns
- snip- 
# 

```

* インストールを確認

```
# certbot plugins
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
* dns-pdns
Description: Obtain certificates using a DNS TXT record (if you are using
PowerDNS for DNS).
Interfaces: Authenticator, Plugin
Entry point: EntryPoint(name='dns-pdns',
value='certbot_dns_pdns.dns_pdns:Authenticator', group='certbot.plugins')

[...]
```
