## Paths

- `.` is the current directory.
- `..` is the directory that contains the current directory.
- `~` is the home directory.
- `/` \(by itself\) is the root directory.

Paths can be combined
- `~/Desktop` is the path to your desktop.
- `../myFile.txt` is the file `myFile.txt` located in the above directory.
- `../../otherFile.txt` is the file `otherFile.txt` located two
 directories above the current directory.

## See Working Directory

- `pwd` prints the working directory to the terminal.

## Listing Files/Folders

- `ls` list the files in the working directory.
- `la` lists all files \(including hidden\). Shortcut for `ls -a`
- `ls <path>` lists the files in the specified directory

## Changing Directories

- `cd <path>` change the working directory to the specified path.

Examples:
- `cd ~` changes you to the user's home directory.
- `cd /` changes you to the root directory.
- `cd ..` changes you up one level in the directory path.
- `cd ~/Desktop` changes to your desktop directory.

## Copying a File

- `cp <source-file-path> <dest-file-path>`

If the dest-file does not exist, one will be made.

Examples:
- `cp myFile.txt myFile2.txt` copies `myFile.txt` into a file called `myFile2.txt` in the current directory.
- `cp ../thatFile.txt thisFile.txt` copies `thatFile.txt` from the above
directory into the file `thisFile.txt` in the current directory.

## Copying a Directory

- `cp -r <source-directory-path> <dest-directory-path>`

If the dest-directory-path does not exist, one will be made.

Example:
- `cp -r myDirectory ../newLocation` copies the directory `myDirectory`
and its contexts to a new directory `newLocation` in the above directory.

## Moving a File

- `mv <file-path> <dest-path>` moves the file to a new location and name.

Examples:
- `mv thisFile.txt thatFile.txt` moves the contents of the file `thisFile.txt` to a new file `thatFile.txt` in the same directory.
This really just renaming the file.
- `mv myFile.txt ./project/newFile.txt` moves the contents of the file
`myFile.txt` the file `newFile.txt` at a subdirectory.

## Deleting a File

- `rm <file-path>` deletes the file at the specified path.

Examples:
- `rm myFile.txt` deletes the file `myFile.txt` in the current directory.
- `rm ../otherFile.txt` detets the file `otherFile.txt` in the above directory.
