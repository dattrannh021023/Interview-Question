# • Unpack test.tar.gz without man pages or google.

To unpack a `tar.gz` file without using man pages or searching online, you can rely on your knowledge of basic tar commands. The essential tar commands are often straightforward:

To extract a `.tar.gz` file, you can use the following command:

```bash
tar -xzvf test.tar.gz

```

Here's what each part of the command does:

- `tar`: Invokes the tar command.
- `x`: Specifies that you want to extract files.
- `z`: Indicates that the file is compressed with gzip.
- `v`: Enables verbose mode to display the progress and list of files being extracted.
- `f`: Specifies the filename of the archive you want to extract, which, in this case, is `test.tar.gz`.

So, when you run the command above, it will extract the contents of `test.tar.gz` to the current directory.