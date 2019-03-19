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

Copy `bin/kerclean` into a location in your `$PATH~. I prefer `~/bin/`.

To run:

```
$ kerclean
```

If you are not root, you will be prompted to run as sudo.

The script will always prompt before making changes. Additionally, it is always safe to run, even
if there are no changes to make. Therefore, it can be used as a utility to simply list what
kernels are installed, which is active for your current session, and which will be active on
next boot.
