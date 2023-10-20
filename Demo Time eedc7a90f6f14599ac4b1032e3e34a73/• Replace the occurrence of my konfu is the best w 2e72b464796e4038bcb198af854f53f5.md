# • Replace the occurrence of "my konfu is the best" with "I'm a linux jedi master" in all *.txt files.

To replace the occurrence of "my konfu is the best" with "I'm a Linux Jedi master" in all "*.txt" files within a directory and its subdirectories, you can use the `find` and `sed` commands together. Here's how you can do it:

```bash
find /path/to/directory -type f -name "*.txt" -exec sed -i 's/my konfu is the best/I'\\''m a Linux Jedi master/g' {} \\;

```

Replace `/path/to/directory` with the actual path to the directory where you want to start the search and replace operation.

This command uses `find` to locate all "*.txt" files in the specified directory and its subdirectories and then executes `sed` on each of those files to perform the replacement. The `-i` option of `sed` is used to edit the files in place, and the `s/old-text/new-text/g` syntax is used to specify the replacement. The single quotes (`'`) are used to ensure that the text containing single quotes is correctly interpreted.