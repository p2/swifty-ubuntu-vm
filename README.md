Swifty Ubuntu VM
================

Vagrant script to setup a Ubuntu (Xenial) VM that has Swift installed and mounts a shared macOS directory.

Uses `curl` to load the given Swift release (3.0.2 currently) into `ubuntu`s home directory, expands and prepends the directory to `PATH`.

Also mounts the directory at `../Ubuntu-Share` on the host to `/macOSshare` inside the VM as a shared directory.
