---
layout: post
title: Simple Progress Status in Python
modified:
categories: til
excerpt:
tags: [python]
image:
  feature:
date: 2016-02-15T21:56:13+01:00
---

Want to display progress status, without additional packages or dependendies?
Here's a simple solution:
{% highlight python %}
print ''
for idx in range(num_rows):
  vec = X[idx]
  process(vec)
  if idx % 100 == 0:
    print '\rProcessed %d/%d (%.2f%%)' % (idx+1, num_rows, (idx+1)*100.0/num_rows)
{% endhighlight %}
The `\r` moves the carriage to the beginning and overwrites the previous progress line.
