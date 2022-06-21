# Introduction

This PKGBUILD for `makepkg` applies the HiDPI / 4K display scaling patch described here: https://groups.io/g/linuxham/message/47205

It needs to be built with fltk-1.4 or newer (currently in development)

# Building and Installing on Arch Linux

Here's what worked for me:

1. Build and install `fltk-git` from [AUR](https://aur.archlinux.org/packages/fltk-git)
1. Clone this repo
1. Run `makepkg` in the repo base directory (resolve any build dependencies, etc)
1. Run `sudo pacman -U fldigi-4.1.22-2-x86_64.pkg.*` to install

# What it changes

[Here's what fldigi looks like without the patch, on a 4K display](https://imgur.com/JqxEsbV)

[Here's what it looks like with the patch](https://imgur.com/hZ5JBft)
