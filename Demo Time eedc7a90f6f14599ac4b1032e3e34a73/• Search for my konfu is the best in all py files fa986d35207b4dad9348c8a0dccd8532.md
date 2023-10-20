# • Search for "my konfu is the best" in all *.py files.

To search for the phrase "my konfu is the best" in all "*.py" files within a directory and its subdirectories, you can use the `grep` command. Here's how you can do it:

```bash
grep -r "my konfu is the best" /path/to/directory/*.py

```

Replace `/path/to/directory` with the actual path to the directory where you want to start the search. This command will recursively search for the specified phrase in all "*.py" files within that directory and its subdirectories and display any matching lines.

If you want to perform a case-insensitive search (i.e., it will match "My Konfu is the Best" as well), you can use the `-i` option:

```bash
grep -ri "my konfu is the best" /path/to/directory/*.py

```

This will also search for the phrase in a case-insensitive manner.