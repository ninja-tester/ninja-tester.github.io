---
layout: article
title:  "How to solve Error code: SEC_ERROR_UNKNOWN_ISSUER while recording JMeter script with Firefox"
date:   2019-01-15 22:00:00 +0400
categories: jmeter
image:
 teaser: jmeter_logo.jpg
 feature: /2019-01-15-sec_error_unknown_issuer/SEC_ERROR_UNKNOWN_ISSUER.png
---

Some load testers are facing an secured connection error while recording JMeter script on Mozilla Firefox:

{% highlight sql %}
Error code: SEC_ERROR_UNKNOWN_ISSUER
{% endhighlight %}

You may follow steps from this post to fix that `SEC_ERROR_UNKNOWN_ISSUER`:

1. Remove all old certificates from your browser and Windows.
2. Press Start record in [HTTP(S) Test Script Recorder][script-recorder]. You will see JMeter alert:
	![alert](/images/2019-01-15-sec_error_unknown_issuer/JMeterRootCACertificate.png)  
3. Install new just created certificate in your browser (`ApacheJMeterTemporaryRootCA.crt` located in your `JMeter\bin` directory).
4. Do actions with your web application to record requests.


How to remove old and add new certificates in Firefox:

1. Start Firefox
2. Open menu
3. Options
4. Privacy & Security
5. View Cerificates
6. Ensure there are no certificates with names "_DO NOT INSTALL..", "DO NOT INSTALL..", "JMETER.." and other related to JMeter cerificates, or Delete them if they are present.
7. Click Import.
8. Navigate to your JMeter bin dir and choose `ApacheJMeterTemporaryRootCA.crt` file.
9. Check Trust this CA to identify websites.
10. Press Ok

![alert](/images/2019-01-15-sec_error_unknown_issuer/FirefoxCertificate.png)

[script-recorder]: https://jmeter.apache.org/usermanual/jmeter_proxy_step_by_step.html#script-recorder