# • Write a script to list all the differences between two directories.

You can use the `diff` command to list the differences between two directories in Linux or Unix-like systems. Here's a simple shell script that takes two directory paths as arguments and uses `diff` to display the differences:

```bash
#!/bin/bash

# Check if two directory paths are provided as arguments
if [ $# -ne 2 ]; then
    echo "Usage: $0 directory1 directory2"
    exit 1
fi

dir1="$1"
dir2="$2"

# Check if both paths are directories
if [ ! -d "$dir1" ] || [ ! -d "$dir2" ]; then
    echo "Both arguments must be directories."
    exit 1
fi

# Use diff to compare the directories and display the differences
diff -r -q "$dir1" "$dir2"

```

Save this script to a file (e.g., `compare_directories.sh`), make it executable with `chmod +x compare_directories.sh`, and then run it with two directory paths as arguments. It will use `diff` to recursively compare the contents of the two directories and list the differences.

For example:

```bash
./compare_directories.sh /path/to/directory1 /path/to/directory2

```

The script will provide a summary of the differences between the two directories, including files that exist in one directory but not the other and files that differ in content.