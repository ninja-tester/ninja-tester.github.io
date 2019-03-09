---
layout: article
title:  "How to reach and use the Sampler, Thread Group and Test Plan names in JMeter"
date:   2019-01-31 20:00:00 +0400
categories: jmeter
image:
 teaser: 2019-01-31-how-to-use-jmeter-thread-sampler-testplan-names/jmeter_logo.jpg
 feature: 2019-01-31-how-to-use-jmeter-thread-sampler-testplan-names/feature.png
---

In some cases in our load test scenarois we need to get the sampler, thread group or even test plan names ans save them as varables.

For example you can send email notification with text like this:
{% highlight sql %}
"Test plan ${testPlanName} get error with ${errorCode} in ${samplerName} running by ${threadGroupName}"
{% endhighlight %}

To accomplish this we have three functions, so we may use them in BeanShell:


1. `__samplerName()`   function returns the name (i.e. label) of the current sampler. The function does not work in Test elements that don't have an associated sampler. For example the Test Plan. Configuration elements also don't have an associated sampler. However some Configuration elements are referenced directly by samplers, such as the HTTP Header Manager and Http Cookie Manager, and in this case the functions are resolved in the context of the Http Sampler. Pre-Processors, Post-Processors and Assertions always have an associated Sampler.  
Example: `${__samplerName()}`  

2. `__TestPlanName()` function returns the name of the current test plan (can be used in Including Plans to know the name of the calling test plan). Example:  
	`${__TestPlanName}`<br>
Note, that `__TestPlanName` will return the *File name* of Test Plan, which can be different with Test Plan Name.

3. `__threadGroupName()` function simply returns the name of the thread group being executed.
Example: `${__threadGroupName}`

 - [JMeter with BeanShell Guide][4]  
 - [BeanShell website][5]

  [4]: https://www.redline13.com/blog/2018/06/testing-complex-logic-with-jmeter-beanshell/
  [5]: http://www.beanshell.org/