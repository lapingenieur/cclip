# cclip

*the console clipboard*

## What is `cclip` ?

You surely already got stuck in a tty needing to copy & paste something, but there's no clipboard in ttys;
`cclip` is a kinda clipboard that works with tty as well as with graphical environments (needs a CLI).

## How to install cclip ?

`cclip` is just a bash script, therefore you only need to download it and make it executable :
(you'll surely need to do these actions as root, just preceed all the commands with `sudo`)

```bash
wget https://raw.githubusercontent.com/lapingenieur/cclip/master/cclip -O /usr/local/bin/cclip -nv
chmod a+x /usr/local/bin/cclip
```

## Usage

### To copy from stdin (standard in)

```bash
&lt;your command> | cclip
```

This will redirect `<your command>`'s  output into cclip's clipboard.

### To print the content of the clipboard

```bash
cclip -o
```

This will print out value stored in cclip's clipboard. You can add redirection/piping to use it elsewhere:

```bash
cclip -o | &lt;your command>
cclip -o >> &lt;your file>
```

This will pipe (give) the stored value to `<your command>` or output its content to `<your file>`
(at the end of file, look at bash redirection for more infos)

### To copy a given string

```bash
cclip -s &lt;your string>
```

This will save `<your string>` in cclip's clipboard.

### To delete/reset the clipboard's content

```bash
cclip -d
```
This will reset the cclip clipboard to be void (to contain "") (this doesn't delete the file)

## Files

`cclip` itself needs to be in a directory part of the `$PATH` variable (as every program should).
It stores its clipboard in `/tmp/cclip`. As this file is in `/tmp` :

* every user can access it
* it is deleted at every reboot
* it is often loaded in the ram (tmp is usually mounted as a ramfs partition)

---

For more infos about cclip execute `cclip --help` in the shell (once installed).

The source code is open source and hosted over my [github page](https://github.com/lapingenieur/cclip).
It is readable/editable/redistributable. Feel free to suggest modifications and open pull requests !

Written by lapingenieur using [neovim](https://github.com/neovim/neovim) (&lt;= best editor! :D)
Hosted over [github](https://github.com/lapingenieur/cclip)
Contact: lapingenieur@gmail.com
