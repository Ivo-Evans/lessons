# mv

Today we're going to learn about the mv command. It stands for 'move', and it takes two arguments

```
mv <this> <here>
```

Each argument should be an address in your filesystem. Both arguments can use filepaths starting from the current working directory or from home, and both need to include the filename and, if applicable, its extension.

Pretty simple. The thing is, mv is _also_ the command for renaming things. If the second parameter is a filename that doesn't exist, mv renames the first. Try it. 

```
mkdir test-dir
touch test
nano test # now write some stuff inside test and press ^x, y, enter, as prompted
mv test test-dir/test
cd test-dir
ls
mv test at-my-behest
ls
cat at-my-behest
```

## Explanation

What we think of as a dual behaviour is actually a single behaviour, because the filesystem in computers are organised according to a concept called _namespace_. The namespace of an environment is the set of possible names in that environment. For instance, say you allowed names that were ten characters long and you allowed 26 characters in each place. A given environment would have 26**10 possible names. When you create a _folder_, it creates a new environment, with a unique namespace inside the folder. It's a beautifully simple system, really. 