# • ./configure shows an error that libfoobar is missing on your system, how could you fix this, what could be wrong?

If `./configure` reports that a required library, such as `libfoobar`, is missing on your system, it means that the software you are trying to build has a dependency on this library, and it couldn't find it in the standard library paths. Here are steps to fix this issue:

1. **Install the Missing Library**:
    
    First, you should check whether the `libfoobar` library is installed on your system. If it's not installed, you need to install it. The process for installing libraries can vary depending on your Linux distribution:
    
    - On Debian/Ubuntu systems, you can use `apt-get` or `apt` to install packages. For example:
        
        ```bash
        sudo apt-get install libfoobar-dev
        
        ```
        
    - On Red Hat/Fedora systems, you can use `yum` or `dnf`. For example:
        
        ```bash
        sudo yum install libfoobar-devel
        
        ```
        
    - On CentOS systems, you might need to enable the EPEL repository first:
        
        ```bash
        sudo yum install epel-release
        sudo yum install libfoobar-devel
        
        ```
        
2. **Check Library Paths**:
    
    After installing the library, if you still encounter the same error, it's possible that the library is installed but not in a directory that `./configure` is searching by default. You can specify additional library search paths using the `LD_LIBRARY_PATH` environment variable. For example:
    
    ```bash
    export LD_LIBRARY_PATH=/path/to/libfoobar:$LD_LIBRARY_PATH
    
    ```
    
    Replace `/path/to/libfoobar` with the actual path to the directory containing `libfoobar.so`. After setting this environment variable, re-run `./configure`.
    
3. **Re-run configure**:
    
    Once you have installed the missing library and/or updated the library search paths, run `./configure` again:
    
    ```bash
    ./configure
    
    ```
    
4. **Check configure Output**:
    
    Carefully review the output of `./configure` after running it again. It should now detect the presence of the `libfoobar` library. Make sure there are no other missing dependencies or errors reported. If there are additional missing libraries or dependencies, repeat the process to install them.
    

By following these steps, you should be able to resolve the issue where `./configure` reports a missing library (`libfoobar`) on your system and continue with the software installation process.