---
layout: article
title:  "How to setup proxy in JMeter"
date:   2010-09-20 17:00:00 +0400
categories: jmeter
image:
 teaser: jmeter_logo.jpg
 feature: surf-through-proxy-server.png
---

If you are testing with JMeter through a proxy, you need to pass proxy settings to JMeter. To do so, run the jmeter.bat/jmeter file from a command line with the following parameters:


>`-H [proxy server hostname or ip address]`  
`-P [proxy server port]`  
`-N [nonproxy hosts] (e.g. *.apache.org|localhost)`  
`-u [username for proxy authentication - if required]`  
`-a [password for proxy authentication - if required]`  

Example : `jmeter -H my.proxy.server -P 8000 -u username -a password -N localhost`

Alternatively, you can use `--proxyHost, --proxyPort, --username, and --password` 