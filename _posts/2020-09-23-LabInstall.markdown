---
layout: post
title:  "Lets set up our Hacking Lab"
date:   2020-09-23 19:17:42 -0600
categories: 
---
For my first post lets learn how to setup our hacking lab in virtualbox. 



To download our hacking lab setup script, open terminal and paste in:

{% highlight bash %}
wget https://raw.githubusercontent.com/beauknowstech/WebApp-Lab-Setup/master/WebApp-Lab-Setup.sh
{% endhighlight %}

Before we go running any rando script from the internet, lets check and see what is under the hood first. Make sure you understand what this script does.
{% highlight bash %}
cat WebApp-Lab-Setup.sh
{% endhighlight %}

Now that we are cool with what the script does, we need to make it executeable:
{% highlight bash %}
chmod +x WebApp-Lab-Setup.sh
{% endhighlight %}
Then to run the script:
{% highlight bash %}
./WebApp-Lab-Setup.sh
{% endhighlight %}

This script should install everything we need to get started right here locally in Docker. 

Check out my [YouTube Channel][youtube-link] for more tutorials and walkthroughs.

[youtube-link]: https://youtube.com/c/beauknowstechstuff