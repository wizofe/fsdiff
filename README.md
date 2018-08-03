# NAME 

fsdiff - A tool to compare filesystems or local disk images. It performs both a content analysis and a 
It can mount and compare two images locally or it can just compare two filesystems.

# SYNOPSIS

`fsdiff [-h] [-v] [--fs-from PATH_FS1] [--fs-to PATH_FS2]`

# DESCRIPTION

fsdiff is a very simple tool used to compare recursively the filesystem directory and file structure.
It does not only perform a quick (shallow) comparison using `os.stat` (stat system call), it also compares 
the contents of the files. In case they differ, it displays a brief summary report. It is also installed
as a Python packaged, so it can be used likewise.

Example run:
`fsdiff ./fs1 ./fs2`

In case a more detailed investigation of the file differences needs to be performed, it's suggested to use
a deep checking tool like diffoscope or Beyond Compare, if a GUI is preffered.

To install you need to `pip install -e .` and then run the `bin/fsdiff`.

Note: Python 3.x is required, a few new language features are used, like `subprocess.run` method as well as the cache
 clearing from the directory compare library. It also needs to be run with super user privileges.

# GENERAL OPTIONS

```
-h
: Displays a help message
--version
: Shows the current version
--fromfs
: The left side filesystem to be compared 
--tofs
: The right side filesystem to perform the comparison with
```