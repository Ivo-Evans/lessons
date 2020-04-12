# Navigating the filesystem within the command line

The commands I'm going to teach you today are all related to navigation. They are 'safe' commands, because they are just about travelling and looking.

So, open up your terminal, enter pwd, and hit enter.

pwd stands for 'print working directory' and it is where you are now.

Now type ls.

ls stands for 'list' and it lists the content of the working directory. However, you can also give it _arguments_, which modify its usage. For instance,

```
	ls -a
```

lists hidden files, such as system files, as well as visible ones.

You can also provide the name of a folder which is in the current working directory as an argument to ls, and then ls will list the contents of _that_ directory.

Finally, cd stands for change directory. Let's say that after using ls, you know that your working directory contains my-folder. You can use cd to move into it

```
	cd my_folder
	pwd
```

what if you want to go back? I'm going to teach you two ways. The tilde (~) is an alias for your 'home' directory. Wherever you are in the filesystem, ~ means 'your home', whatever that happens to be. I believe that on macs home is the desktop.

Another symbol is two dots(..). This means 'this directory's parent directory'. It allows you to go up a single layer, relative to where you are now.

These addresses, like a filename, should be separated from the command by a space.

The challenge, if you can call it such, is just to move around your filesystem, getting to know these three commands. They'll pay dividends!