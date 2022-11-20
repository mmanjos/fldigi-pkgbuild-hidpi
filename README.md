# Introduction

This PKGBUILD for `makepkg` applies the HiDPI / 4K display scaling patch described here: https://groups.io/g/linuxham/message/47205

This is a modification of [work by mmanjos](https://github.com/mmanjos/fldigi-pkgbuild-hidpi) to instead pull the latest fldigi source from git since the source package that repo used seems to be no longer available. I also increased the scale factor -- you can adjust the scale factor (currently `45.0`) in `hidpi-fix.patch` to adjust it more. (A smaller number means larger text/scale.)

It needs to be built with fltk-1.4 or newer (currently in development)

# Building and Installing on Arch Linux

Here's what worked for me:

1. Build and install `fltk-git` from [AUR](https://aur.archlinux.org/packages/fltk-git)
1. Clone this repo
1. Run `makepkg -si --skipinteg` in the repo base directory (resolve any build dependencies, etc) to build and install

# What it changes

[Here's what fldigi looks like without the patch, on a 4K display](https://imgur.com/JqxEsbV)

[Here's what it looks like with the patch](https://imgur.com/hZ5JBft)
