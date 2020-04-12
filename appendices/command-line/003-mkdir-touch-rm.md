# modifying the filesystem

Note that these commands are for linux and mac. The pc equivalent of touch is new-item. (If you're using PC, you might want to consider WSL2, or dual-booting Ubuntu.) 

Yesterday you explored the command line a bit: today you'll do some more exploring, except that instead of merely navigating, you'll explore its creative and destructive powers, with mkdir, touch and rm.

mkdir makes a directory. Give the directory a name like this

```
  mkdir my-dir
```

give it multiple names separated by spaces to make multiple directories.

touch creates a file, unless there is already a file of that name in the working directory, and then it does nothing - like the inverse of touching a moth's wing. The file is an empty, plain-text file. It doesn't even need a file extension. All files, at base, are like this: even a JPEG is a long string.

rm is for removing things - but there's a catch. rm will remove single files, but if you want to remove folders, you'll need to use rm -r, rm 'recursive'. You can also use man rm, or indeed man any other command, to see a manual page for the command.

So, cd around a bit and try out these commands.