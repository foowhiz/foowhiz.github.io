---
layout: post
title: wifiToggle
---

It's been a while since I posted. I need to start writing more about my discoveries as a programmer.

I wrote a shell script a couple of days ago, called [wifiToggle](https://github.com/foowhiz/wifiToggle). I got irritated by the bad hostel Wi-Fi here. Somehow, Ubuntu keeps disconnecting from the hostel internet, and to connect it back, either I have to wait for a few minutes (Like I'm gonna do that when I don't have internet), or I can switch the Wi-Fi off and on.

The issue was, there's too many clicks to get to the "Turn off Wi-Fi" button, and then again to turn it on. So I thought of making a keyboard shortcut. Easy enough, all I needed was a shell script, and I could link it to a custom keyboard shortcut through settings in Ubuntu.

The steps to use this script are given in the readme file in the repo. There's one interesting thing though. While assigning the path of the script in the keyboard shorcut, giving the path with ```~``` for home doesn't work. Rather, the full path, i.e., ```/home/username/...``` needs to be given. This is because while bash recognizes ```~``` as ```$HOME```, the custom keyboard shortcut maker doesn't.
