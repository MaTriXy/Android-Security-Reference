# Root Overview

Root is just another userspace user with extended (or rather, not limited) permissions.

Many android users root their device to allow 3rd party apps access to restricted `system` permissions to perform previously restricted functionality.

Rooting a device is a contentious subject as many domain-sensitive applications would rather not run on a rooted device, as if the device is rooted as a result of malware (or a rooted device has since been compromised by malware) the attack surface is much larger. This leads to a cat-and-mouse scenario between root-detectors and root-hiders (discussed elsewhere in this folder).

## Links

- [Is there a difference between sudo mode and kernel mode?](http://stackoverflow.com/questions/21761185/is-there-a-difference-between-sudo-mode-and-kernel-mode)
  - Interesting and needs more research _"However, the superuser may have the ability to change kernel code, for example by asking the kernel to load a module or by modifying the storage from which the kernel is loaded on boot. Finally, in some cases the superuser may be able to execute calls which expose raw hardware or memory to userspace access, and subsequently perhaps do some things from userspace which can ordinarily only be done from kernel space."_
- [What Is “Systemless Root” on Android, and Why Is It Better?](https://www.howtogeek.com/249162/what-is-systemless-root-on-android-and-why-is-it-better/)
  - Systemless = modified boot image
  - System = flash su binary to system (or custom ROM)
