# Boot, Reboot and Shutdown

As is often the case in Linux, the are multiple solutions to this. Obviously to boot you simply turn the computer on, that much is obvious.

Everything else you make calls to the _Init_ system, which in RHEL7 is [systemd](https://en.wikipedia.org/wiki/Systemd).

To reboot choose one of:

```
   reboot
   systemctl reboot
   shutdown -r now
```

To shutdown choose one of:

```
   poweroff
   systemctl poweroff
   shutdown -p
```

You can also do timed reboots and shutdowns using the `shutdown` command. For example to power off a system after a delay of 25 minutes run:

```
   shutdon -p 25
```

<aside class="notice">
The Linux boot process is:

Bios boots Bootloader (GRUB2), boots kernel, boots init system (systemd), which starts your services
</aside>



# Boot systems into different runlevels manually



# Use single-user mode to gain access to a system

# Identify CPU/memory intensive processes, adjust process priority with renice, and kill processes

# Locate and interpret system log files

# Access a virtual machine's console

# Start and stop virtual machines

# Start, stop, and check the status of network services
