# Navigation, Links, and File Viewing Commands

This file documents Linux commands related to directory navigation, file
linking, and viewing file contents.

---

## Hard Links and Soft Links

### Hard Links
 
 - Syntax: ln file1 file2
 - Creates another reference to the same inode (data on disk). Both files share
   the same inode and changes to one reflect in the other. Deleting one does not
   remove the data unless all links are removed. Cannot span filesystems.

### Soft Links

 - Syntax: ln -s file1 file3
 - Points to the pathname of another file. Has its own inode and acts like a
   shortcut. Can span filesystems and breaks if the target file is deleted.


## Directory Stack Navigation

### pushd

 - Syntax: pushd /path/to/directory
 - Saves the current directory and moves to a new one. Useful for temporarily
   moving between directories.

### popd

 - Syntax: popd 
 - Returns to the last directory saved by pushd.

### dirs

 - Syntax: dirs
 - Displays the directory stack


 
## Viewing file contents


### cat
 - Syntax: cat filename
 - Displays the contents of a file. Best for small files.

### tac
 - Syntax: tac filename
 - Displays the file contents in reverse order.

### less
 - Syntax: less filename
 - Views file contents one screen at a time.
	- Can scroll up/down
	- Search with /
	- Quit with q

### head
 - Sytax: head filename
 - Displays the first 10 lines of a file.

### tail
 - Syntax: tail filename
 - Displays the last lines of a file


## Notes
 - Hard links reference data directly; soft links reference paths
 - `less` is preffered over `cat` for large files
 - Directory stack commands help with efficient navigation
