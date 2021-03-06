---
layout: post
title: 'Dagr: A Time of the Day Based LED Lighting System'
date: 2014-03-25 01:52:03.000000000 -06:00
comments: true
---



Because I tend to be more focused and productive at late night, I usually stay up late working on some stuff that needs to be done. 

Most of the time these stuff involves using my PC, and [staying up late in front of a screen messes up with our sleep](http://chriskresser.com/how-artificial-light-is-wrecking-your-sleep-and-what-to-do-about-it), as it [lowers our bodies melatonin production](http://www.webmd.com/sleep-disorders/news/20030620/nighttime-computer-users-may-lose-sleep). So unless I worked until I felt exhausted, there was no way I could fall asleep within 30 minutes of going to bed.

That was before I discovered [F.lux](http://justgetflux.com) a software that adapts your screen to the time of the day. Basically it decreases your screen [color temperature](http://en.wikipedia.org/wiki/Color_temperature) at night, and becomes warmer the later at night it is. On their website they even have [more information and a collection of links to research documents about light exposure effects on sleeping](http://justgetflux.com/research.html). 

[F.lux]((http://justgetflux.com)  solves my watching the screen in the dark troubles, but when I needed to do stuff at my desk and not on the screen, all I had was my cool white desk lamp.

## Dagr ##
Inspired by F.lux, I decided to make my own light system that changes the color temperature according to the time of the day. 

<!-- more -->

So with an [Arduino UNO](http://arduino.cc/en/Main/arduinoBoardUno), a [BLE shield](http://www.seeedstudio.com/depot/Bluetooth-40-Low-Energy-BLE-Shield-v20-p-1631.html), a [Digital RGB LED strip](http://www.seeedstudio.com/depot/Digital-RGB-LED-FlexiStrip-30-LED-1-Meter-p-1665.html), and a 5V DC adapter to power the strip; I could make an Arduino controlled time-of-the-day based light system.

I cut a strip with 7 LEDs, which was enough to cover a fairly small area just below a bunkbed, where my desk is. Because I haven't bought a case for my Arduino, I built one with some old Lego pieces I found few weeks ago, and used some plastic coated wire to hang it to the ceiling. 

![](/content/images/2015/02/Dagr.jpg)

## Controlling the light ##

The light color temperature can be set automatically according to the current time of your device, manually setting the [color temperature](http://en.wikipedia.org/wiki/Color_temperature) from 1000K to 4000K, or manually setting the individual RGB values from the iOS app.

The communication between the iOS app and the Arduino works between the mobile device's Bluetooth and the Arduino's BLE shield.

The temperature to RGB conversion was made based on [Tanner Helland's algorithm](http://www.tannerhelland.com/4435/convert-temperature-rgb-algorithm-code/) and the daytime based temperature algorithm was made based on my own preference, with three stages of temperature color change:

- 6:00 AM to 8:00 AM
- 6:00 PM to 8:00 PM
- 8:00 PM to 10:00 PM

![](/content/images/2015/02/DagrAction.jpg)

## Wrapping it up ##

With the stuff I mentioned and a few wires, you can have your own Dagr, time-of-the -day based lighting at your home or office. 

You can find the complete code of Dagr for both the iOS app and Arduino are at my repository:
[https://github.com/deivuh/dagr](https://github.com/deivuh/dagr).  

Pull requests for functionality, success stories and comments are all welcome :)

### Update: More about sleep quality ###

Besides screen / light exposure before bedtime, there are a few other factors caused by technology that may affect our sleep quality. A reader made a research about this and wanted to share with us an interesting [article he wrote that covers this topic.](http://www.thesleepjudge.com/different-ways-technology-affects-sleep-quality/) 

### Update 2: Even more information about sleep quality ###

Another reader made a research about electronics and sleep, and made a [nice infographic about ways it affects our sleep and how to protect against it](https://sleepybliss.com/tips-guides/how-electronics-affect-sleep). 
