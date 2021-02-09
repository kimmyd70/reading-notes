# Automation with Python

### ** notes from this article on [python regex](https://www.datacamp.com/community/tutorials/python-regular-expression-tutorial)

** Will need to re-reference this tutorial often

See the article for Regex tutorial including functions `compile(), search(), findall(), sub() for search and replace, split(), match(), group()`

Don't forget `import re`

Use `r` at the start of the pattern to indicate raw string literal

### ** notes from this article on [shutil](https://pymotw.com/3/shutil/)

Performs high-level file operations such as copying and archiving

Don't forget `import shutil`

`shutil.copyfile()` copies contents of source to destination or raises IOError if permission problems

`shutil.copy()` interprets the output name like CLI cp creating a new file using the base name, etc.  File permissions are copied along with contents

`shutil.copy2()` same as `copy()` but includes the access and modification times in the metadata

`shutil.copymode()` duplicates permissions to the new file

`shutil.copystat()` duplicates permission and dates associated with the original file

`shutil.copytree()` recurses through the source working tree and duplicates to the destination.  Includes two arguments. Also, `rmtree()` `move()`  to work with existing files/trees

`shutil.which()` scans, and filters to find files

`shutil.get_archive_formats()` has info on the ways it can be used to archive

`shutil.disk_usage()` for local file system information

## ** this video on [automation ideas](https://www.youtube.com/watch?v=qbW6FRbaSl0&t=69s)

## ** this video on [automating browser and desktop apps](https://www.youtube.com/watch?v=dZLyfbSQPXI)

## ** this article on [Watchdog](https://pythonhosted.org/watchdog/) to monitor file system events
