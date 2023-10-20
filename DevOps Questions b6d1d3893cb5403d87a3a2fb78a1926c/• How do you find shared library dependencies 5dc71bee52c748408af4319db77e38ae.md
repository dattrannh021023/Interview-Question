# • How do you find shared library dependencies?

To find shared library dependencies for an executable or a shared library in Linux, you can use several command-line tools. Two common options are `ldd` and `objdump`. Here's how you can use both:

1. **Using ldd**:
    
    The `ldd` command displays the shared library dependencies of an executable or a shared library.
    
    Syntax:
    
    ```bash
    ldd /path/to/executable_or_library
    
    ```
    
    For example:
    
    ```bash
    ldd /bin/ls
    
    ```
    
    This will print a list of shared libraries that the specified executable or library depends on.
    
2. **Using objdump**:
    
    You can also use `objdump` to inspect the dynamic section of an executable or shared library to find the required shared libraries.
    
    Syntax:
    
    ```bash
    objdump -p /path/to/executable_or_library | grep NEEDED
    
    ```
    
    For example:
    
    ```bash
    objdump -p /bin/ls | grep NEEDED
    
    ```
    
    This command extracts and lists the required shared libraries.
    

Both of these methods will give you a list of shared library dependencies for the specified executable or library, allowing you to see which libraries it relies on.