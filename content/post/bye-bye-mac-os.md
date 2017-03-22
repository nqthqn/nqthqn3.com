+++
date = "2017-02-02 05:05:48"
draft = "false"
title = "Bye bye Mac OS"
slug = "bye-bye-mac-os"

+++

And hello Ubuntu. I've downloaded my [ISO](https://www.ubuntu.com/desktop). Here's how I got it on my thumb drive,

 - First run `diskutil list` then insert your usb stick
 - `diskutil list` again to see the disk node (e.g. `/dev/disk2`).
 - `diskutil unmountDisk /dev/diskN`
 - `sudo dd if=/path-to.iso of=/dev/rdiskN bs=1m` (note the `rdisk`, `r` is for `raw` and makes this process faster.
 - Stare and wait. There is no feedback.
 - When finished `diskutil eject /dev/diskN`