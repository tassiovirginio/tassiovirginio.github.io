---
title: "Archlinux Repositories Trends"
date: 2023-09-08T08:06:25+06:00
description: "Archlinux Repositories Trends"
menu:
  sidebar:
    name: "Archlinux Repositories Trends"
    identifier: archlinuxrepositoriestrends
    weight: 40
hero: boat.jpg
mermaid: true
---

### Archlinux is a well known distro...

and somewhat dreaded by newbies in the linux world. It's a Rolling Release distribution, which means you'll always have the newest versions of your libraries “in theory”. Like any other distro Archlinux packages go through a process to enter their "stable" version, being one of the fastest existing distributions "if not the fastest".

Arch your package management is very open, at https://archlinux.org/packages/ you can search for any package you want, it will have information about the package like: package name, what version current, the maintainer, the last person who sent the package, package size, among other information (figure below).

___

Another feature is that the package can be marked as out of date, as seen in the example in the figure below.

___

Another highlight of Archlinux is its “AUR” user repository, where any user can post their package, which is actually a PKGBUILD file, with all the instructions to install the application/library on arch.

___

Arch's package system uses git to manage its packages, anyone can create an account on the AUR website and upload their package through git. Or you can download an existing package and update it.

___

As seen in the figure above we have the option to write a comment about the package, this action sends a notification to the maintainer of the package, which can “or not” respond to your comment. A lot of the Archlinux community likes iteration, not that they're very friendly, but in my experience they're pretty methodical.

I finally got to the part that gives the theme to this article, with all this control over your packages, Archlinux manages to generate statistics for its users. And with this data there is a website (https://pkgstats.archlinux.de/fun) that gives us an interesting insight into its users.

___

This site brings us information about: Browsers, Editors, Desktops, File Managers, Window Manager, Shells, among others. From this we can see the characteristics (of the majority) of Archlinux users, starting with the browser, which highlights Firefox, followed by Chromium, then Google-Chrome, as we can see in the figure below. I found it interesting that Chromium has no second place, I always had the impression that it wasn't used much (a nice surprise).

___

Now let's look at the text editors, which highlights Nano, followed by VI, and then Vim. Something to notice is the drop Nano and Vi are having, and the rise of Vim.

___

And finally the Desktop Environments data, something interesting to note is that GNOME SHELL 3 had a high use since its release (2011), and somehow remained stable until today, XFCE had a growth at that time since the release of GNOME SHELL, has been stable for a while and has started to decline lately. KDE Plasma 5 was released in 2014 and since its release it has not stopped growing, standing out in the chart, having the most prominent curve, surpassing GNOME SHELL and XFCE.

___

This data is only from a distribution, but Archlinux is a distribution that leaves in the user's hands which applications he will want to use, of course the data in this same way from an Ubuntu or Pop-OS distribution would probably bring very different data, but they are ready-made distributions. What Archlinux's data brings is its users' raw choices, showing the preferences of each type of package they want to use. I don't see many trendy distributions using Plasma, and we're always under the impression that few people use it, but apparently, at least among Archlinux users, it's well used. I would like to remind you that Archlinux repositories are used by many other distributions, such as Manjaro, Endeavor and others.

How is this data going in this year of 2021? Are we going to have surprises?

To the next…