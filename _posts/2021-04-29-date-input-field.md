---
layout: post
title: "Date/Time input fields"
categories: original
author: "Conrad Maaijen"
---

![Browsers](/assets/posts/browsers-input-type.png) { align: center }
Safari 14.1 (shipping this week) also added support for Date & Time form controls.

<!--more-->

Below some examples to test what is working in your browser (and what not)

### Basic support

```html
<input type="datetime-local">
<input type="date">
<input type="time">
<input type="month">
<label><input type="week">
on macOS.
```

<label><input type="datetime-local" name="date"> Date Time local</label><br>
<label><input type="date" name="date"> Date</label><br>
<label><input type="time" name="time"> Time</label><br>
<label><input type="month" name="month"> Month</label><br>
<label><input type="week" name="week"> Week</label>

### Min and max support
Only tested for date, since that is by far the most popular type. Enter a date between 1st of January and 31st of March, 2015.

<label><input type="date" name="dateWithMinMax" min="2015-01-01" max="2015-03-31"> Date</label>
