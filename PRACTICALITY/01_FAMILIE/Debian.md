Linux Kernel
     │
   Debian
     │
   Ubuntu
     │
 Linux Mint

> BUT => Kernel → Debian → Ubuntu → Mint

- It's not : Kernel → Debian → Ubuntu → Mint

Instead: Ubuntu is a separate Linux distribution based on Debian.

And:Linux Mint is a separate distribution based largely on Ubuntu.

So think: 

                 Linux Kernel
                      │
                   Debian
                      │
              ┌───────┴───────┐
              ↓               ↓
           Ubuntu        other Debian-based
              │             distributions
              ↓
         Linux Mint

> Ubuntu uses Debian as a foundation, while making its own choices and additions. => summary

# Example:- 

Android
APK
 ↓
application package

Debian/Ubuntu
DEB
 ↓
software package

# Summary 

Ubuntu
 ↓
Debian-based
 ↓
.deb packages
 ↓
apt
 ↓
dpkg underneath

````bash
"What is dpkg?"

Low-level Debian package tool that directly handles .deb packages.

If I say:

"What is apt?"

Higher-level package-management tool that handles repositories, downloading, dependencies, installation, updates, etc.

```
