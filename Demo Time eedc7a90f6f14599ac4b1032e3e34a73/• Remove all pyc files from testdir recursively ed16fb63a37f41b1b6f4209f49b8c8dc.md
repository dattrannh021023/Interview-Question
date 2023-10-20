# • Remove all "*.pyc" files from testdir recursively?

To remove all "*.pyc" files from the "testdir" directory and its subdirectories recursively, you can use the `find` command along with the `rm` command. Here's the command:

```bash
find testdir -type f -name "*.pyc" -exec rm -f {} \\;

```

Let's break down what this command does:

- `find testdir`: Starts searching from the "testdir" directory.
- `type f`: Specifies that it should only look for files (not directories).
- `name "*.pyc"`: Filters files with the ".pyc" extension.
- `exec rm -f {} \\;`: Executes the `rm -f` command for each found file, removing it. The `{}` is a placeholder for the file name, and `\\;` marks the end of the `exec` command.

This command will find and delete all "*.pyc" files within the "testdir" directory and its subdirectories.