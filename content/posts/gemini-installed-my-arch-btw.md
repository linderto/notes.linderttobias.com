+++ 
draft = false 
date = 2026-01-19T18:17:13+01:00
title = "Gemini installed my Arch Linux, btw"
description = ""
slug = ""
authors = []
tags = []
categories = []
externalLink = ""
series = []
+++

Six minutes and 134,000 Gemini 3.0 tokens;  Thats all it took for Gemini to set up a functional Arch Linux system with LUKS on LVM, Hyprland, and Waybar using a bootable USB ISO.

Recently, I have been toying with different Linux distributions. While I am very happy with my current setup (Ubuntu + Hyprland), there are definitely valid arguments for other distros like Fedora, Debian, or Arch[^1]. While Fedora uses the “Anaconda” GUI installer, Arch Linux is DIY by nature. It forces you to build the system from the ground up, which significantly boosts your understanding of the vast GNU/Linux ecosystem.

Thanks to a detailed documentation in the [Arch Wiki](https://wiki.archlinux.org/title/Installation_guide), I was able to get Arch running “relatively” quickly on a spare Schenker laptop with encrypted disks, successfully porting my Hyprland work environment. (Needless to say, mistakes were made; my first reboot resulted in a corrupted boot drive. It took some more tries and troubleshooting to get the system exactly how I wanted it.)

Once the system was tailored to my needs, I did the only “sane” thing I could think of: I inserted the bootable USB again, booted into the live environment, and wiped my disks to start from zero. I then installed gemini-cli in the live environment, entered the “YOLO Mode” (STRG+Y) with Gemini 3.0[^2] and supplied the agent with the following prompt:

> “You are an expert Linux System Admin and a passionate Arch Linux user. Performance and Security are your priorities. You are currently on a live ISO of Arch. Install Arch on the system successfully with LUKS, LVM, Hyprland, and Waybar. Additionally, there is an extra USB drive with multiple dotfiles; install and configure them.”

6 minutes and 42 seconds later, it was done. Skeptical, I restarted my laptop, and there it was. Encryption was working. The display manager was functional. Hyprland was running smoothly, and even Waybar appeared (more or less). While not everything worked perfectly (some shortcuts and Waybar modules needed fixing), I was quite happy with how it turned out, especially since my dotfiles were originally optimized for my Ubuntu ThinkPad.

I could not have asked for more. However, I’ll still do it manually next time[^3]

[^1]: I have been running my Ubuntu + Hyprland setup quite successfully for a while, but was increasingly running into limitations when needing up-to-date packages. I also wanted to experiment with cutting-edge features, which often required manually building these packages because they had not yet been published for Ubuntu (or never will be). Additionally, I was always enviously surveying the AUR for package versions that were a couple of major and minor versions ahead of Ubuntu.
[^2]: I tried the same prompt several times with Gemini 2.5 Pro; it failed each time with the encryption step, and the system could not boot up successfully on its own afterwards.
[^3]: There are lots and lots of reasons to do this manually. “Just Because You Can, Doesn’t Mean You Should”.
