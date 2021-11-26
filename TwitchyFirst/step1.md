# ulimit
## *ulimit* is a built-in bash command that displays or resets a number of resource limits associated with processes running under a shell. 
```bash
> ulimit -a
```

```
-t: cpu time (seconds)              unlimited
-f: file size (blocks)              unlimited
-d: data seg size (kbytes)          unlimited
-s: stack size (kbytes)             8192
-c: core file size (blocks)         0
-m: resident set size (kbytes)      unlimited
-u: processes                       30593
-n: file descriptors                1024
-l: locked-in-memory size (kbytes)  64
-v: address space (kbytes)          unlimited
-x: file locks                      unlimited
-i: pending signals                 30593
-q: bytes in POSIX msg queues       819200
-e: max nice                        0
-r: max rt priority                 0
-N 15:                              unlimited
```
> **Note** 
> 
> This only affects the current shell.
> For permanent changes, edit ```/etc/security/limits.conf``` and then reboot
---
# ldd
## *ldd* can be used to ascertain what shared libraries an executable requires. It shows the soname of the library and what file it actually points to.
```bash
> ldd /usr/bin/nano
```
```
  	linux-vdso.so.1 (0x00007ffd0056c000)
	libmagic.so.1 => /lib64/libmagic.so.1 (0x00007fd12cbf0000)
	libncursesw.so.6 => /lib64/libncursesw.so.6 (0x00007fd12c9b3000)
	libtinfo.so.6 => /lib64/libtinfo.so.6 (0x00007fd12c786000)
	libc.so.6 => /lib64/libc.so.6 (0x00007fd12c3c1000)
	libz.so.1 => /lib64/libz.so.1 (0x00007fd12c1aa000)
	libdl.so.2 => /lib64/libdl.so.2 (0x00007fd12bfa6000)
	/lib64/ld-linux-x86-64.so.2 (0x00007fd12d053000)
```
> **Note** 
> 
> The file ```/etc/ld.so.conf``` lists the directories that will be searched for shared libraries
---
# Kernel Upgrade (Fedora)
## When you install a new kernel on your system, it requires a reboot to take effect
```bash
> sudo rpm -ivh kernel-{version}.{arch}.rpm
```
> **Note** 
> 
> You should not perform an upgrade with '-U' for a kernel because this direct upgrade would remove the currently running (old) kernel.
 
> **Note 2** 
> 
> After this is done, the GRUB configuration file will be updated to include the new kernel version automatically and it will be the default choice when you reboot.

---
# netstat
## Use netstat to find processes listening to ports
```bash
> netstat -tulpen | grep portNo
```
---
# file
## Use *file* to discover the type of data inside a file, even without an extension
```bash
> file my_python_script_wrongext.sh
```
```
my_python_script_wrongext.sh: Python script text executable, ASCII text
```
---