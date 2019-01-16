---
layout: post
title: "Formatting Ellapsed Time in Python"
tags: [software, python]
---

The following code snippet is a quick way to format raw ellapsed time (ms) into a readable format.

```
'''
Output the ellapsed time in a timestamp format
:time_ms - time from zero in milliseconds
:return - 00:00:00.000 - formatted timestamp containing hours:minutes:seconds.microseconds
'''
def format_ellapsed_time(time_ms):
    t = timedelta(seconds=(time_ms/1000.0))
    hours, remainder = divmod(t.total_seconds(), 3600)
    minutes, seconds = divmod(remainder, 60.0)
    return '{:02d}:{:02d}:{:06.3f}'.format(int(hours), int(minutes), seconds)
```
