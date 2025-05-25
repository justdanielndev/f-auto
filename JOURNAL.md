---
title: "fAuto"
author: "Daniel"
description: "Bringing Android Auto to my unsupported car with the help of a Raspberry Pi"
created_at: "2025-05-24"
---

# May 24th: First iteration

Today I tried to get a version of OpenAuto running on my Pi 3 B+. I ended up settling for [CrankShaft](https://github.com/opencardev/crankshaft) as the base OS because it seemed to be the easiest one to set up, but it looks like I was heavily mistaken. Not only is the wiki extremely outdated and doesn't apply to the latest version 99% of the time, most guides also don't even work anymore :3 which means that I wasn't really able to get the OS to even launch at all.

So, I did what any sane person would do (irony) and started going around the Pi's filesystem, enabled devmode and did some experimentation. It took me about 1.2 hours to get an old 7" screen I had running around to turn on (yeah... I honestly don't know why I didn't give up :D), but after changing the kernel settings for a bit, I managed to force set HDMI compatibility and make the Pi actually detect the screen. First challenge solved!

*But*, as it always happens with all of my projects, something broke again, in this case touch compatibility. I wasted around 2 hours trying to get it fixed, and in the end I left it off as something for future me, as no solution worked and I actually had to completely reinstall the whole OS once :D

Next the challenge was to get Android Auto actually running. While I want to get wireless functionality to work in the future, wired is ok with me for now. I tested it with my phone and (wow, so unexpected) another error! This time DPI imploded and the screen looked awful, but after fiddling a bit with settings on both kernel and android auto I got it fixed! :D

Once Android Auto managed to work, I decided to try and work with implementing video and audio input + output. Audio output was quite easy as the Pi 3 is one of the model that actually supports 3.5mm jack output, so that was quite an easy success! As for audio input... Well, it seems like the Pi wants to receive it via USB, so that's something that I'll need to add to the BOM as I don't have any that can work with it at all. I also tried to set up camera input but it seemed to want to receive input from the actual car telling it that it is going backwards, which my car won't let me do... So I guess that's a no :(

After all this hassle and also working on my other project, I decided to go to sleep and mark the day as completed.

**Total time spent: 6h**

# May 25th: Second version

Today I decided to plan the rest of the features (hardware!), which are going to be the hardest. First off, I told myself that I had to move away from the "half falling apart" design I had before (the cables work only in certain positions and are too big and long, and the current "case" is a cardboard cutout 🤣).

So, I started to search for components. I searched for good, short Micro USB (male) to USB (male) cables on both Amazon and AliExpress and settled for [this ones](https://www.amazon.es/gp/product/B094Q9TKZR/), which for just 7€ will allow me to connect screen data and power to the Pi. Then, for the HDMI, I went for [this one](https://www.amazon.es/PNGKNYOCN-ascendente-velocidad-adaptador-compatible/dp/B08S7D6GH7/), as it features a 90º angle that makes it easy to implement and doesn't use too much space. Finally, to connect the Pi to the car, [this charger](https://www.amazon.es/PNGKNYOCN-ascendente-velocidad-adaptador-compatible/dp/B08S7D6GH7/) and [this cable](https://www.amazon.es/VBESTLIFE-Raspberry-universal-alimentaci%C3%B3n-Interruptor/dp/B07BLRR29C/) as (believe it or not) none of the microusb cables seem to want to work with the Pi, as the ones I have are too old and don't even support 3A (most people only have USB-C cables nowadays...).

Finally, I searched for a fan + heatsink so that the Pi doesn't overheat (has happened to me way too many times) and shuts down. I ended up going for [this pack](https://www.amazon.es/GeeekPi-enfriamiento-Raspberry-disipador-Ventilador/dp/B07JGNF5F8/), which has both heatsink and fan.

And you may ask: "Daniel, you mentioned needing a microphone but didn't actually appear in your parts research!". Well, I managed to trick the Pi into thinking my camera was a microphone, and managed to use its integrated mic! So, one item we can skip :D

After knowing which parts I'd use, I wanted to do the actual case for the headunit, so I went ahead and opened Fusion to design it in 3D.

I started doing a rough first version, which ended up like this: ![3D view 1](https://github.com/justdanielndev/f-auto/blob/main/3D.png?raw=true)

This is just a first rough sketch that I'll try to improve on the coming days, so stay tuned! I want to add a logo, slots for more components like a light sensor (if I have time, though it's something I do want to implement), etc.

**Total time spent: 3h (yeah, Fusion took more than I expected it to...)**
