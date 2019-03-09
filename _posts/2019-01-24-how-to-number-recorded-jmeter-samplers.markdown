---
layout: article
title:  "How to number recorded JMeter samplers"
date:   2019-01-24 21:00:00 +0400
categories: jmeter
image:
 teaser: jmeter_logo.jpg
 feature: 2019-01-24-how-to-number-recorded-jmeter-samplers/matrix.jpg
---

JMeter has the ability to number recorder samplers in semi-automatic mode.
For recording, you need to add to the HTTP (S) Test Script Recorder to test plan.
Next we do the following with it:

1. Select HTTP (S) Test Script Recorder
2. Open the "Test Plan Creation" tab
3. In the Grouping combo box, select "Put each group in a new transaction controller"
4. In the HTTP Sampler Settings block, select the "Prefix" rule.
5. In the text field to the right of it we indicate the first prefix, for example "1.1." - this value will be added to the name of each recorded request.
6. Specify after what time (in milliseconds) a new Transaction Controller will be created for requests.

	![alert](/images/2019-01-24-how-to-number-recorded-jmeter-samplers/https_script_recorder.png)  

During the recording process, this window will appear, with which we can manage the naming:

![alert](/images/2019-01-24-how-to-number-recorded-jmeter-samplers/recorder_transaction_controls.png)  

Here, if we need to write the next block, we change the prefix - after that, for the following requests, a new Transaction Controller will be created with such a prefix.

Check out some more tips on [how to write a test in JMeter][jmeter-recording-tips]


[jmeter-recording-tips]: https://www.redline13.com/blog/2016/01/jmeter-recording/