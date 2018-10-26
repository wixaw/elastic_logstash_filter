# Elastic Logstash Filter

Exemples de filtres logstash pour radiusd, sendmail, ltmp, imap et apache

Valide pour les logs envoyés par filebeat au format syslog sous Centos 7

Organisation des fichiers : 

```
├── conf.d
│   ├── root-ca.pem
│   ├── template-apache.json
│   └── template-maillog.json
├── conf.d_piped
│   ├── p1-filebeat.conf
│   └── p2-rsyslog.conf
├── logstash.yml
├── patterns
│   ├── maillog
│   │   ├── imap.grok
│   │   ├── lmtpunix.grok
│   │   └── sendmail.grok
│   └── radiuslog
│       └── radiuslog.grok
└── pipelines.yml
```

Exemple format de log :
```
radius > (123456)  Login OK: [toto] (from client nomSwitch port 1 cli BB-FF-11-99-DD-AA via TLS tunnel)
imaps > login: [111.112.113.114] toto plaintext+TLS User logged in SESSIONID=<mail.domaine.fr-12345-12345678-1>
```

Source grok radius : https://github.com/mcnewton/elk/blob/master/grok-patterns/freeradius

Source grok sendmail : https://github.com/tykling/logstash-grok-patterns/blob/master/patterns/sendmail/sendmail.grok
