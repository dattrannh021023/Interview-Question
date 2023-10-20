# • How to reboot server when reboot command is not responding?

When the "reboot" command is not responding on a Linux server, it can be a challenging situation. In such cases, you can try the following alternative methods to initiate a server reboot:

1. **Using "shutdown" Command**:
You can try using the "shutdown" command to reboot the server with the "-r" option, which specifies a reboot. Open a terminal and run:
    
    ```bash
    sudo shutdown -r now
    
    ```
    
    The "now" parameter means to initiate the reboot immediately.
    
2. **Force Reboot with Magic SysRq Key**:
The Magic SysRq key is a mechanism to communicate directly with the kernel, even when the system is unresponsive. To trigger a reboot, you can use this key combination:
    1. Press and hold the "Alt" and "SysRq" (Print Screen) keys.
    2. While holding these keys, type the following keys one at a time, with a short pause between each key: R, E, I, S, U, B.
    
    This sequence will safely unmount file systems and initiate a reboot. It's a last resort method and should only be used when other options fail.
    
3. **Power Cycle the Server**:
If none of the above methods work, and you have physical access to the server or remote management capabilities (e.g., through a remote power switch), you can perform a hard reset by power cycling the server. However, this should be a last resort as it can result in data loss or filesystem corruption.
4. **Contact Data Center or Hosting Provider**:
If the server is hosted in a data center or by a hosting provider, you may need to contact their support team for assistance with rebooting the server if you do not have physical access or remote management capabilities.

It's important to note that forcibly rebooting a server can potentially lead to data corruption or other issues, so always try to gracefully shut down the server using the "shutdown" command or other appropriate methods first. Use forceful methods like the Magic SysRq key or power cycling only when necessary and after considering the potential consequences.