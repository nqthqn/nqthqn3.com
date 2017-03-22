+++
date = "2017-01-10 03:32:37"
draft = "false"
title = "*nix adventure #1: fun files"
slug = "nix-adventure-1"

+++

Load your electron guns and prepare for the light emitting diodes; We're going to linux land. You have arrived in a strange location some where on the hard drive. Where could you be in this vast universe? `/home/root` most likely. Who are you? `root` I would presume. There's no place like `~`.

### Let's begin.

First things first.

- `whoami`

Will print out who you are now — your current username. Let's hope it's something beautiful.

- `pwd`

`P`rint `W`orking `D`irectory will... do that. Did I mention everything starts at `/` in linux land?

- `ls`

This will `l`i`s`t the files in the current `w`orking `d`irectory :). Is there anything hiding out there in the bleak darkness?

- `ls -a`

Oh my! A flag (`-a`)! This shows us `a`ll the hidden files - those sneaky albeit useful files prefixed with a `.`. Like `.bashrc` for example.

- `cd`

Want to start your adventure now? Do you know who and where you are? Then go ahead and `c`hange `d`irectories. I suggest visiting `/`. So run `cd /`.

I wonder what could be in here? An `etc`? A `bin`? This will depend on your flavor of *nix.

#### Let's do some things with files.

 - `cd` to get home
 - `mkdir leet` to make a directory called `leet`
 - `cd leet` to `c`arefully `d`ive into that directory ([info](https://en.wikipedia.org/wiki/Leet))
 - `touch foo` to make a file called `foo`
 - `echo '1 l0v3 l34rn1n6 l1nux' >> foo` to append that silly string to the file
 - `cat foo` to spit the contents of `foo` to `stdout` ([info](http://stackoverflow.com/questions/3385201/confused-about-stdin-stdout-and-stderr))
 - `vi foo` or `nano foo` to edit the file
   - In vim: `i` to insert, `ESC` `:` `wq` to write the file and quit
 - `cp foo foo1` make a copy of foo called foo1
 - `mv foo1 foo2` rename foo1 to foo2
 - `ls` take a look at your hard work
 - `cd ..` to go up a directory

Try experimenting with `touch`, `cp`, `mv`, `ls`, `cd`, `pwd`. I'll add more adventures soon. I also plan to make this one a bit more "fun".
