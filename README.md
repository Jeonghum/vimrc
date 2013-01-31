## News
- Install script(install.sh) is added     2013.1.31
- LLVM vimrc is added                     2013.1.30
- LICENSE of LLVM is added and applied    2013.1.30
- Install Guide is updated                2013.1.30

## About

### .vimrc
- Makes vim more useful to work on C/C++/Java projects
  (and possibly other projects too)
- Includes many useful short-cut key mappings
- Includes many useful vim plugins (via Vundle)

### mkcscope.sh
- Good script to generate cscope.out

### mkctags.sh
- Good script to generate ctags

Testing environment
- Ubuntu 12.04

Prerequisite
- git-core vim exuberant-ctags cscope

Note

.inc file and .def file are treated as C++ source file.
All the places related this is listed below.
- mkcscope.sh :
   ```
   -o -name '*.inc' -o -name '*.def'
   ```
- mkctags.sh :
   ```
   --langmap=C++:+.inc+.def
   ```


## Install Guide
### Clone Journeyer's repository
```
$ git clone git://github.com/Journeyer/vimrc.git
```

This makes new directory 'vimrc', which is your local reposiory clone.
If you are on Ubuntu, you can simply install using install script.

```
cd vimrc
./install.sh
```

You must provide sudo password for doing this DURING the install.
But DO NOT invoke this script under sudo command your self.
Just run it without sudo and provide sudo password when you are asked.

```
provide sudo password
```

And after the script finished it's job, you Open vim and :BundleInstall
your self.

```
vim
:BundleInstall
```

If you are not on Ubuntu or want to install manually
follow instructions below.


### Install .vimrc

1. Backup your .vim/ and .vimrc in your home directory if they exist
   ```
   $ cd ~
   $ mv .vim/ vim_backup/
   $ mv .vimrc vimrc_backup
   ```

2. Create symbolic links to the .vimrc files checked-out

   ```
   $ ln -s -T vimrc/.vimrc .vimrc
   $ ln -s -T vimrc/.llvm.vimrc .llvm.vimrc
   ```

3. Install Vundle

   ```
   $ git clone https://github.com/gmarik/vundle.git ~/.vim/bundle/vundle
   ```

   (Refer to https://github.com/gmarik/vundle)

4. Open vim and :BundleInstall

   ```
   $ vim
   :BundleInstall
   ```


### Install mkcscope.sh & mkctags.sh

1. Go to /usr/local/bin

   ```
   $ cd /usr/local/bin
   ```

2. Create symbolic links to mkcscope.sh and mkctags.sh

   ```
   $ sudo ln -s -T ~/vimrc/mkctags.sh mkctags.sh
   $ sudo ln -s -T ~/vimrc/mkcscope.sh mkcscope.sh
   ```


## Using scripts

There is a rule to use these scripts.
- Generate ctags and cscope.out (by running mkcscope.sh and mkctags.sh)
  in a top directory of your project
   ```
   $ mkctags.sh
   $ mkcscope.sh
   ```

   To close cscope after cscope finished it's job, press CTRL+D.

- Open vim from the top directory of your project

   If you open vim other places than where those tags files exist,
   vim cannot use those tags files.

   If you don't need to use tags files along with vim,
   you can open vim anywhere you want.

## Feedback Hunted

Any feedback including contributing is highly hunted.
- Some good vim script snippets,
- Some good settings,
- Some good configurations,
- Some good vim plugin,
- Your opinion about the current vimrc file and
- Bug report,
- etc. (Lunch or coffee is a possible Mandatory!! ^^;)

Your happy use of these small scripts is surely welcome.


## TODO
- Install script must support other linux distributions
  and Unix, Mac, and even Windows hopely.
- Project specific settings in mkctags.sh and mkcscope.sh have to be seperated
  into project specific different files so that
  open scripts only contains common general settings


## References

- http://kldp.org/node/125263
- http://kldp.org/
- http://stackoverflow.com/
- http://kangcom.com/sub/view.asp?sku=201008310017&mcd=571
- http://llvm.org/docs/CodingStandards.html#coding-standards

Thanks to the authors and contributors (known and unknown) above,
we could happy vim.


Journeyer J. Joh

