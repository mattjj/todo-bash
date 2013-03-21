Two tiny programs, `todo` and `todone`. I like to alias them to `t` and `d`.

# Usage #

Here's an example usage with the aliases:

```bash
$ t feed the plants
1. feed the plants
$ t water the cat
1. feed the plants
2. water the cat
$ t
1. feed the plants
2. water the cat
$ t brush the cat
1. feed the plants
2. water the cat
3. brush the cat
$ d cat
!! multiple matches !!
2. water the cat
3. brush the cat
$ d brush
1. feed the plants
2. water the cat
$ d 1
1. water the cat
$ tail -5 $TODOHISTORY
+ feed the plants; Wed Mar 20 23:49:37 EDT 2013
+ water the cat; Wed Mar 20 23:49:39 EDT 2013
+ brush the cat; Wed Mar 20 23:49:54 EDT 2013
- brush the cat; Wed Mar 20 23:50:37 EDT 2013
- feed the plants; Wed Mar 20 23:50:39 EDT 2013
```

The lists are just plain text files, so it's easy to open them up and edit them
by hand whenever that's necessary.

# Installation #

Clone the repo somewhere on your `$PATH`, like maybe `~/bin` if you use that:

```bash
git clone git@github.com:mattjj/todo-bash.git ~/bin/todo
```

These programs require an environment variable `TODOFILE` be set to a path at
which the todo list will be stored as a plain text file. There are also a
couple optional variables. You might add something like this to your `.bashrc`
or `.zshrc`:

```bash
export TODOFILE=~/Dropbox/todo/todo
export TODONEFILE=~/Dropbox/todo/todone
export TODOHISTORY=~/Dropbox/todo/.todo-history
alias t=todo
alias d=todone
```

or this to your `config.fish`:

```fish
set -x TODOFILE ~/Dropbox/todo/todo
set -x TODOHISTORY ~/Dropbox/todo/todo-history
set -x TODONEFILE ~/Dropbox/todo/todone
alias t=todo
alias d=todone
```
