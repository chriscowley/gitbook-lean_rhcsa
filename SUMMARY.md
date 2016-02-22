# Summary

Studying for RHCSA

* [Essential Tools](book/01-essential_tools.md)
* [Operate Running Systems](book/02-operate_running_systems.md)
* [Configure Local Storage](03-configure_local_storage/README.md)
    * List, create, delete, and set partition type for primary, extended, and logical partitions.
    * Create and remove physical volumes, assign physical volumes to volume groups, and create and delete logical Volumes.
    * Create and configure LUKS-encrypted partitions and logical volumes to prompt for password and mount a decrypted file system at boot.
    * Configure systems to mount file systems at boot by Universally Unique ID (UUID) or label.
    * Add new partitions and logical volumes, and swap to a system non-destructively.
* [Configure Filesystems](04-configure_filesystems/README.md)
    * Create, mount, unmount, and use ext2, ext3, and ext4 file systems.
    * Mount, unmount, and use LUKS-encrypted file systems.
    * Mount and unmount CIFS and NFS network file systems.
    * Configure systems to mount ext4, LUKS-encrypted, and network file systems automatically.
    * Extend existing unencrypted ext4-formatted logical volumes.
    * Create and configure set-GID directories for collaboration.
    * Create and manage Access Control Lists (ACLs).
    * Diagnose and correct file permission problems.
* [Deploy, Configure and Maintain systems](05-deploy_configure_maintain/README.md)
    * Configure networking and hostname resolution statically or dynamically.
    * Schedule tasks using cron.
    * Configure systems to boot into a specific runlevel automatically.
    * Install Red Hat Enterprise Linux automatically using Kickstart.
    * Configure a physical machine to host virtual guests.
    * Install Red Hat Enterprise Linux systems as virtual guests.
    * Configure systems to launch virtual machines at boot.
    * Configure network services to start automatically at boot.
    * Configure a system to run a default configuration HTTP server.
    * Configure a system to run a default configuration FTP server.
    * Configure a system to use time services.
    * Install and update software packages from Red Hat Network, a remote repository, or from the local file system.
    * Update the kernel package appropriately to ensure a bootable system.
    * Modify the system bootloader.
* [Manage Users and Groups](06-users_and_groups/README.md)
    *  Create, delete, and modify local user accounts.
    * Change passwords and adjust password aging for local user accounts.
    * Create, delete, and modify local groups and group memberships.
    * Configure a system to use an existing LDAP directory service for user and group information
* [Manage security](07-security/README.md)
    * Configure firewall settings using system-config-firewall or iptables.
    * Set enforcing and permissive modes for SELinux.
    * List and identify SELinux file and process context.
    * Restore default file contexts.
    * Use boolean settings to modify system SELinux settings.
    * Diagnose and address routine SELinux policy violations

