---
layout:	post
title:	"Some handy tips for vim beginners"
date:	2017-04-14 12:00:01
categories: open-source 
author:	rahul
---

Following are some nifty tips for vim noobs. By noobs I'm referring to people who have basic knowledge of it's keybindings and make their way around editing a simple file.

---

### 1. Start editing files with single instance of Vim

If you use vim as open a file, save and close, open another one, there are better ways to do so. Vim supports multiple files editing at once. It's not apparant as there's no indication by default (like a sidebar or something). To open more files in vim, one can use:

	:e <filename>

---

### 2. Buffers

When editing multiple files, each one is assigned a buffer. In case viewing a single window, the remaining buffers are behind it. Use, 

	:buffers		//For listing buffers
	
	:bn			//For switching to next buffer

	:bp			//Previous one

	:b <buffer name>	//Specific one

---

### 3. Splits

Vim also supports split windows. One can edit the same file in different splits too, like having the top portion of a file in one vertical split, and editing the bottom portion in the other split (it's useful, believe me). 

	:sp <filename>		//For opening a new file in a horizontal split

	:vsp <filename>		//Same thing, but for vertical split

	:sb <buffername>	//Horizontally split and open buffer

	:vert sb <buffername>	//Vertically split, and open buffer

Alternatively one can use **sbn**, where *n* represents buffer number.

---

### 4. Tabs

Tabs are a bit unconventional in vim. I personally don't find much use of it, unless I've to open an out of context file. People generally use tabs to have different window configuration of same files. [Some quick tips for using tabs efficiently](http://vim.wikia.com/wiki/Quick_tips_for_using_tab_pages).

---

### 5. Shell commands

Just use an exclamation mark before the command. Quite helpful for me when I wish to build a tool, without closing vim or opening another shell. For instance,

	:!make

--- 

### 6. Miscellaneous

* Copy someone else's *vimrc* file, by writing it yourself line by line. Helpful if you want to customize that further. Hundreds available online. Mine is way too primitive, so not sharing that. 

* Create your own custom key mappings. Like, for tabs, you can use the conventional tabs key mappings (`Ctrl-t`).

* There's a built-in file explorer. Use **:Ex** for that.

* There's no by default in-vim shell (-1 for vim, +1 for emacs), but you can always open a new shell instance from vim. Use **:sh** for that. Better yet, use `Ctrl-d` key binding for that. So you can open shell by `Ctrl-d` and close the shell by same.

* There are hundreds of plug-ins available (including some for in-app shell). [Pathogen](https://github.com/tpope/vim-pathogen) would come quite handy.
