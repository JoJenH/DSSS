Damn Small SQLi Scanner [![Python 3.x](https://img.shields.io/badge/python-3.x-yellow.svg)](https://www.python.org/) [![License](https://img.shields.io/badge/license-Public_domain-red.svg)](https://wiki.creativecommons.org/wiki/Public_domain)
=========

**Damn Small SQLi Scanner** (DSSS) 是一个用仅仅不到100行代码编写，却功能完善的 [SQL注入](https://en.wikipedia.org/wiki/SQL_injection) 漏洞扫描工具 (支持GET与POST参数)。

![Vulnerable](http://i.imgur.com/7mXeXjF.png)

支持可选设置：HTTP代理与HTTP头值' User-Agent '， ' Referer '和' Cookie '。

如何运行
----

```
$ python3 dsss.py -h
Damn Small SQLi Scanner (DSSS) < 100 LoC (Lines of Code) #v0.3a
 by: Miroslav Stampar (@stamparm)

Usage: dsss.py [options]

Options:
  --version          show program's version number and exit
  -h, --help         show this help message and exit
  -u URL, --url=URL  Target URL (e.g. "http://www.target.com/page.php?id=1")
  --data=DATA        POST data (e.g. "query=test")
  --cookie=COOKIE    HTTP Cookie header value
  --user-agent=UA    HTTP User-Agent header value
  --referer=REFERER  HTTP Referer header value
  --proxy=PROXY      HTTP proxy address (e.g. "http://127.0.0.1:8080")
```

```
$ python3 dsss.py -u "http://testphp.vulnweb.com/artists.php?artist=1"
Damn Small SQLi Scanner (DSSS) < 100 LoC (Lines of Code) #v0.3a
 by: Miroslav Stampar (@stamparm)

* scanning GET parameter 'artist'
 (i) GET parameter 'artist' could be error SQLi vulnerable (MySQL)
 (i) GET parameter 'artist' appears to be blind SQLi vulnerable (e.g.: 'http://t
estphp.vulnweb.com/artists.php?artist=1%20AND%2061%3E60')

scan results: possible vulnerabilities found
```

依赖
----

[Python](http://www.python.org/download/) version **3.x** is required for running this program.
