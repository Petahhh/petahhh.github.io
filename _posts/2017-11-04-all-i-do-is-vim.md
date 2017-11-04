---
layout: post
title:  "All I do is VIM VIM VIM"
date:   2017-11-04 16:33:29 -0500
---

![win]({{ "/assets/win.gif" }})

I love keyboard shortcuts. Naturally, VIM would be my best friend but it was really hard to get into. While pair programming at Pivotal with expert VIMists (is that a word?) I got to learn a few tricks. Below I've gathered a subset of vim commands that have converted me. Think of it as "just enough vim" to get very comfortable.

I assume you understand the difference between insert, visual and normal mode.

# Basics

`dd` deletes the line your cursor is on
![dd]({{ "/assets/dd.gif" }})

`x` deletes the character you cursor is on 
![x]({{ "/assets/x.gif" }})

`D` deletes all the characters from your cursor to the end of the line 
![D]({{ "/assets/D.gif" }})

`r` + `<some character>` will replace the character your cursor is on with `<some character>`
![r]({{ "/assets/r.gif" }})

`p` will paste what you've copied in the line below your cursor
![p]({{ "/assets/p.gif" }})

`P` will paste what you've copied in the line above your cursor
![P]({{ "/assets/shiftp.gif" }})

`y` will copy the highlighted text

![y]({{ "/assets/y.gif" }})

`yy` will copy the line your cursor is on
![yy]({{ "/assets/yy.gif" }})

# Movement

`j`, `k`, `h` and `l` will move your cursor down, up, left and right respectively
![j]({{ "/assets/j.gif" }})
![k]({{ "/assets/k.gif" }})
![h]({{ "/assets/h.gif" }})
![l]({{ "/assets/l.gif" }})

`gg` will jump you to the top of the file
![gg]({{ "/assets/gg.gif" }})

`G` will jump you to the bottom of the file
![G]({{ "/assets/G.gif" }})

`0` will move you to the front of the line
![0]({{ "/assets/0.gif" }})

`$` will move you to the end of the line
![dollar]({{ "/assets/dollar.gif" }})

## "Scrolling"

I use these two often to "scroll" through a file. `{` will move your cursor to the next empty new line above your cursor

![previousempty]({{ "/assets/previousempty.gif" }})

`}` will move your cursor to the next empty new line below your cursor
![nextempty]({{ "/assets/nextempty.gif" }})

Alternatively you can use `ctrl+f` or `cftrl+b` to scroll to the previous or next "page" where page is the amount of lines that your screen can fit. I find i don't use this as often.
![page f]({{ "/assets/pagef.gif" }})
![page b]({{ "/assets/pageb.gif" }})

## Text manipulation

`ciw` will delete the word you're  cursor is on and put you in insert mode. I remember this as "change in word"

![ciw]({{ "/assets/ciw.gif" }})

`viw` is similar to `ciw` but only highlights the word and puts you in visual mode. I remember this as "view in word"

![viw]({{ "/assets/viw.gif" }})

`d/` + `<some characters>` + `enter` will delete characters from your cursor to `<some characters>`. This is equivalent to highlighting and deleting part of a line in say sublime. 

![dslash]({{ "/assets/dslash.gif" }})

`J` will delete and append the line below your cursor the end of your current line. It's handy when you want to "glue" together some lines of text.

![shiftj]({{ "/assets/shiftj.gif" }})

## Switching to insert mode

`a` puts your cursor in insert mode after the character the cursor was on. `i` puts your cursor in insert mode before the character the cursor was on.
![a]({{ "/assets/a.gif" }})
![i]({{ "/assets/i.gif" }})

`A` puts your cursor in insert mode at the end of the current line. `I` puts your cursor in insert mode at the beginning of the line.

![shifta]({{ "/assets/shifta.gif" }})
![shifti]({{ "/assets/shifti.gif" }})

To remember which is which I tell myself that `a` stands for append and `i` ... is the other one.

`o` puts you in insert mode on a new line below your current line. `O` puts you in insert mode on a new line above your current line.

![o]({{ "/assets/o.gif" }})
![shifto]({{ "/assets/shifto.gif" }})

## Commands

As a quick summary for complete beginners to VIM, you can enter commands while in normal mode by type `:` followed by the command and `enter`. Here are some basic ones everyone should know.

`:w` saves the current file. I remember it as "writes" the file.

`:q` quits the file.

`:wq` saves the file and quits the file. `:x` is equivalent. Not sure why it exists but I use it often.

`:qa` quits all the buffers.

`:set cursorcolumn` creates a highlight bar on the column your cursor is on. It's just a visual aid which is helpful to check your tabbing is okay.

![cursorcolumn]({{ "/assets/cursorcolumn.gif" }})

`:set nu` turns on line numbers. It's actually short for `:set number` which is easier to remember.

![nu]({{ "/assets/nu.gif" }})

`:set nonu` turns off line numbers. There is also an equivalent `:set nonumber`.

![nonu]({{ "/assets/nonu.gif" }})

`:e <filename>` will open up a file you type in. 

![colone]({{ "/assets/colone.gif" }})

Use `ctrl+o` to move to the previously opened file or `ctrl+i` to move to the next opened file.

![io]({{ "/assets/io.gif" }})

`:set wrap` turns on wordwrapper. Handy when you're editing paragraphs of text and not code. `:set nowrap` will undo the wordwrapper.

![wrap]({{ "/assets/wrap.gif" }})

When you're pasting blocks of text from outside of vim, you should run `:set paste` to prevent vim auto inserting tabs in your text.

### Find / Search

`/` following by a word searches your file for that word. 
![slash]({{ "/assets/slash.gif" }})

Type `n` to move your cursor to the next instance of that word. `N` will move your cursor to the previous one. 

![n]({{ "/assets/n.gif" }})
![shiftn]({{ "/assets/shiftn.gif" }})

A fun fact I later learnt about this is that even after you start editing or move your cursor to another line, `n` and `N` will still work for the last word you searched for.

![moren]({{ "/assets/moren.gif" }})

When you do a find/search vim will highlight that text. Use `:noh` to remove this highlight. I remember it as "no highlight".

![noh]({{ "/assets/noh.gif" }})


### Multiple windows

`:sp` is a handy command that will split your window into two horizontally. (I remember it as "**sp**litting" the window) This is convenient for when you want to look at two different files at the same time. I often follow `:sp` with `:e` to open up new files.

![sp]({{ "/assets/sp.gif" }})

I more commonly use `:vs` which I remember as a vertical split. This splits the screen side by side.
![vs]({{ "/assets/vs.gif" }})

To move around windows you can use `ctrl+w ctrl+w` to toggle your cursor between open windows. To be more exact you can use `ctrl+w (j/k/h/l)` to move in a specific window to the bottom, top, left or right.

![ww]({{ "/assets/ww.gif" }})
![wjk]({{ "/assets/wjk.gif" }})

#### Quickly highlight blocks of texts

`V` will highlight the entire line your cursor is on. Follow through with movements like `j`, `k`, `{` or `}` to highlight large blocks of text. 

![shiftv]({{ "/assets/shiftv.gif" }})
![shiftvplus]({{ "/assets/shiftvplus.gif" }})


## Fancy stuff

So there are a few handy moves that I don't know where to put them. They are definitely outside the basics.

`:%s/existing-string/new-string/g` Will find all instances of "existing-string" and replace it with "new-string"

![percents]({{ "/assets/percents.gif" }})

A variation of the above is `:%s/existing-string/new-string/gc` which replaces instances of "existing-string" one by one but asks you to confirm first. Hit `y` to accept, hit `n` to skip.
![percentsc]({{ "/assets/percentsc.gif" }})

There is this multicursor command: `ctrl+v (j/k/h/l)`. This allows you to select the current column among multiple lines.

![ctrlv]({{ "/assets/ctrlv.gif" }})

More interestingly once you've selected a set of lines, by typing `I <some chars> ESC`, you'll apply `<some chars>` to all the lines that were selecto confirm ted.

![ctrlvplus]({{ "/assets/ctrlvplus.gif" }})

### Markers

If you're editing a large file and are frequently jumping back and forward between two sections you can create markers to quickly jump between lines. `m<somechar>` will allow `` `<somechar>`` to jump to that line. (That's a backtick follow by some character). 

![marker]({{ "/assets/marker.gif" }})

Run `:marks` to see the markers you've set.

## Plugins

There are tons of plugins available for VIM that does very specific things. The one I suggest as a must have is [NERDTree](https://github.com/scrooloose/nerdtree). 

You can use `|` (pipe) to jump from your current file to the tree. Or you can use the same keys for window navigation such as `ctrl+w h` to move to the window to the left since NERDTree is just another window.

![pipe]({{ "/assets/pipe.gif" }})

# Conclusion

If you memorize this subset of commands I'm confident you'll begin to navigate VIM with ease...

And when I step into the building everybody's hands go ... on the keyboard
![hands]({{ "/assets/hands.gif" }})

