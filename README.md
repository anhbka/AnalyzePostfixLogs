### Analysis Postfix Logs via Software Pflogsumm

Statistics of mails received, delivered, forwarded, delayed, bounced, rejected, retained, and discarded; Statistics of senders and recipients; Statistics of sending and receiving hosts/domain names; Count the number of SMTPD connections.


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

### Analysis Postfix Logs via Software Pflogsumm

1. Installation

```
CentOS:  yum install postfix-pflogsumm -y
Ubuntu:  apt-get install pflogsumm -y
```

2. Use command
```
# Email details are counted within 7 days:  pflogsumm  /var/log/maillog
# Count today's email messages:  pflogsumm -d today /var/log/maillog
# Count yesterday's email messages:  pflogsumm -d yesterday /var/log/maillog
# Count messages for specific dates:  pflogsumm "Apr 7" /var/log/maillog 
```
<img src="/img/postfix1.png">

