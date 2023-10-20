# • I've lost my root password, what can I do?

If you've lost the root password on a Linux system, you can regain access by following these steps. The exact method may vary slightly depending on your Linux distribution:

**Note:** To perform these steps, you typically need physical access to the machine or a console connection, or you must be able to reboot the system. If the system is hosted in a cloud environment, you may need to follow your cloud provider's password recovery procedures.

1. **Reboot the System:**
    
    If you can, reboot the system. During the boot process, you might see a bootloader menu (e.g., GRUB) where you can edit the kernel command line.
    
2. **Access Single-User Mode:**
    
    Edit the kernel command line and append `init=/bin/bash` to the end of the line. This will boot the system into single-user mode, where you will have a root shell without requiring a password.
    
    For example, in GRUB, press 'e' to edit the kernel command line, find the line starting with `linux` or `linux16`, and append `init=/bin/bash` to the end. Then press 'Ctrl+X' to boot.
    
3. **Remount the Filesystem as Read/Write:**
    
    The root filesystem is often initially mounted as read-only in single-user mode. You need to remount it as read/write:
    
    ```
    mount -o remount,rw /
    
    ```
    
4. **Change the Root Password:**
    
    Use the `passwd` command to change the root password:
    
    ```
    passwd
    
    ```
    
    You will be prompted to enter a new password twice.
    
5. **Clean Up:**
    
    After changing the password, remount the filesystem as read-only again:
    
    ```
    mount -o remount,ro /
    
    ```
    
6. **Continue the Boot Process:**
    
    Type `reboot` to continue the normal boot process:
    
    ```
    reboot
    
    ```
    
7. **Log in with the New Password:**
    
    Once the system has rebooted, log in with the new root password.
    

Please note that these steps should only be used for legitimate purposes, such as recovering a forgotten password on a system you own or administer. Unauthorized access or password recovery on systems you do not own or have permission to access is illegal and unethical.

Always practice good security hygiene by using strong, memorable passwords and securely storing them to avoid the need for password recovery.