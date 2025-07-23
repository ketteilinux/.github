<h1>Kettei Linux. (Neotesk's Linux Configuration)<img align="left" width="60" height="42" alt="logo" src="https://github.com/user-attachments/assets/303a29c7-9426-4681-8280-0da50891f36e" /></h1>

This is a custom Arch-based configuration that works by hijacking certain core packages inside the Arch Linux Package Repository. It adds custom dependencies to the core packages like [`base`](https://gitlab.archlinux.org/archlinux/packaging/packages/base) and [`filesystem`](https://gitlab.archlinux.org/archlinux/packaging/packages/filesystem).

### Why did you do this?
Because it is fun and I don't want to spend time configuring each piece of the system one by one, over and over again since I reinstall my system occasionally.

### How do I install this?
Here's a diff of how you're going to do that using `/etc/pacman.conf`
```diff
...

+ [kettei]
+ Server = https://ketteilinux.github.io/kettei-depo/$arch

[core]
Include = /etc/pacman.d/mirrorlist
...
```
and for copy-paste, here's the raw version:
```
[kettei]
Server = https://ketteilinux.github.io/kettei-depo/base
```
After doing this, you should install a fresh system using `pacstrap` since updating your current system might result in unforeseen consequences. Make sure that your boot mount points to `/usr/boot/`

### How can I make one?
I recommend you to follow [sainnhe](https://github.com/sainnhe)'s instructions on their blog. [**Here's the blog-post btw**](https://www.sainnhe.dev/post/create-personal-arch-linux-package-repository/)
