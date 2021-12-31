### * Analyze Postfix Logs 

* Download file

```
wget https://raw.githubusercontent.com/anhbka/AnalyzePostfixLogs/main/pflogsumm.pl
cp -rp pflogsumm.pl /usr/local/bin/pflogsumm
chown bin:bin /usr/local/bin/pflogsumm
chmod 755 /usr/local/bin/pflogsumm
```

### * Analyze Postfix Logs 

`cat /var/log/maillog | pflogsumm | more`

<img src="/img/pfsum.png">

### * Use command check logs

`grep "status=sent" /var/log/maillog |cut -d "=" -f 2 |cut -d ">" -f 1 |cut -d "<" -f 2 |sort -n |uniq -c`

<img src="/img/postfix.png">

### * Check email reject
```
grep reject /var/log/maillog
```
