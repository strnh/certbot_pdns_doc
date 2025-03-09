## 作業手順書

### インストール

* pip で security/py-certbot-dns-pns を入れる

```
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

* plugin の クレデンシャルファイルを作成 

~/pdns-credentials.ini

dns_pdns_endpoint = https://pdns-api.example.com
dns_pdns_api_key = <Your API Key>
dns_pdns_server_id = localhost # see https://doc.powerdns.com/authoritative/http-api/server.html
dns_pdns_disable_notify = false # Disable notification of secondaries after record changes

(使用可能な構成オプションは、PowerDNS プロバイダーの DNS-Lexicon 設定に対応)

* plugins を認証プロバイダとして certbot を実行。


certbot certonly \
    --authenticator dns-pdns \
    --dns-pdns-credentials ~/pdns-credentials.ini \
    ...
