# ulimit

## *ulimit* is a built-in bash command that displays or resets a number of resource limits associated with processes running under a shell

```bash
> ulimit -a
```

> **Note**
>
> This only affects the current shell.
> For permanent changes, edit ```/etc/security/limits.conf``` and then reboot

---

# ldd

## *ldd* can be used to ascertain what shared libraries an executable requires. It shows the soname of the library and what file it actually points to

```bash
> ldd /usr/bin/nano
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
> netstat -tulpen | grep 80
```

---

# file

## Use *file* to discover the type of data inside a file, even without an extension

```bash
> file /usr/bin/ls
```

---
