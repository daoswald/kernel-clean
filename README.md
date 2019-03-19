# Kernel Clean

Keep GRUB and kernel list up to date. For CentOS 7.

## Description

This script checks what kernels you have installed on your system. If you have more than five, it will prompt to
remove the oldest kernels.  It also checks what the currently running kernel is, and which one will become
active on next boot (current and default).  If the default kernel is not the newest, you will be prompted
about whether or not to set the newest kernel as default for future boots.

## Getting Started

Clone the repository. Install (to system-Perl) the Perl module Sort::Versions

```
yum install perl-Sort-Versions
```

Copy `bin/kerclean` into a location in your `$PATH`. I prefer `~/bin/`.

To run:

```
$ kerclean
```

If you are not root, you will be prompted to run as sudo.

The script will always prompt before making changes. Additionally, it is always safe to run, even
if there are no changes to make. Therefore, it can be used as a utility to simply list what
kernels are installed, which is active for your current session, and which will be active on
next boot.

## Example run

```
$ bin/kerclean
[sudo] password for userfoo:
4 kernels found:
        (0) 3.10.0-957.10.1.el7.x86_64
(c) (d) (1) 5.0.2-1.el7.elrepo.x86_64
        (2) 5.0.1-1.el7.elrepo.x86_64
        (3) 3.10.0-957.5.1.el7.x86_64

[  (c) Currently active kernel.    (d) Default grub kernel.  ]
```

Had the newest kernel not been the same as the default `(d)` kernel, the user would have been prompted to change
the GRUB setting.  Had there been more than five kernels, the user would have been prompted to remove old
kernels.
