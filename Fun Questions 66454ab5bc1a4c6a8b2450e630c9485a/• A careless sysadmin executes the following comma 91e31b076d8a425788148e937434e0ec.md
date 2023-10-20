# • A careless sysadmin executes the following command: chmod 444 /bin/chmod  - what do you do to fix this?

If a careless sysadmin has changed the permissions of the `/bin/chmod` command to `444`, which makes it non-executable and non-writable, you can still fix this issue by following these steps:

1. **Gain Root or Sudo Access:**
    
    Ensure that you have root access or sudo privileges on the system to make the necessary changes.
    
2. **Use Another System or Live CD (Optional):**
    
    If you don't have root or sudo access, and the system is no longer functional due to this issue, you may need to boot into a rescue environment using a live CD or another system with access to the affected system's disk.
    
3. **Change Permissions:**
    
    You can change the permissions of the `/bin/chmod` command back to their default settings (usually `755`) by running the following command as root or with sudo:
    
    ```
    sudo chmod 755 /bin/chmod
    
    ```
    
    This command will make `/bin/chmod` executable by the root user and other users on the system.
    
4. **Verify Permissions:**
    
    Verify that the permissions have been corrected by running:
    
    ```
    ls -l /bin/chmod
    
    ```
    
    The output should show `chmod` with permissions like `-rwxr-xr-x` (755).
    
5. **Test the Command:**
    
    After restoring the permissions, test the `/bin/chmod` command to ensure it is working as expected:
    
    ```
    /bin/chmod +x /bin/chmod
    
    ```
    
    This command adds execute permissions to `/bin/chmod`, allowing it to be executed again.
    
6. **Review Security:**
    
    After resolving the issue, it's essential to review and improve system security practices to prevent similar incidents in the future. Restricting access to critical system commands and using proper access controls is crucial.
    
7. **Audit and Monitoring:**
    
    Implement auditing and monitoring solutions to keep track of changes to critical files and directories, especially system binaries.
    
8. **Backup and Restore (If Necessary):**
    
    If the incorrect permissions caused problems on the system, and you have backups, consider restoring the affected files and directories from backups to ensure the system is in a consistent state.
    

Always exercise caution when making changes to system files and permissions, as incorrect changes can lead to system instability or security vulnerabilities.