# VIM cheat sheet

## Translations

* [Russian version](./README-ru.md)

## ToDo

* add more info about:
  * search
  * replace
  * go to line
  * go to char in line
  * replace current symbol
* add Screencast GIFs with show-cases
* create github.io page with copyable by click commands
* add best about VIM (vim ide, plugins and other awesome-vim)

## Exit, saving, edit

| Command | Description                                                                                            |
|---------|--------------------------------------------------------------------------------------------------------|
| `:q`    | exit from file                                                                                         |
| `:w`    | save file/write file content                                                                           |
| `:e`    | reload file content                                                                                    |
| `!`     | run command anyway (force run)                                                                         |
| `:wq`   | you can combine commands (in this example, the file will be saved and closed)                          |
| `:x`    | same as `:wq`                                                                                          |
| `ZZ`    | same as `:wq`                                                                                          |
| `:q!`   | you can combine commands (force quit anyway, for example, after the changes made, without saving them) |

## Common usage

| Command        | Description                                                    |
|----------------|----------------------------------------------------------------|
| `i`            | insert / enter mode                                            |
| `a`            | insert / enter mode                                            |
| `ESC (Ctrl+[)` | usual mode                                                     |
| `hjkl`         | moving cursor in different directions                          |
| `o`            | add a line after the current                                   |
| `Shift+o`      | add a line before the current                                  |
| `u`            | undo the last command                                          |
| `Ctrl+r`       | undo the undo the last command(redo) / repeat the last command |
| `gg`           | move cursor to the top of the file                             |
| `Shift+g`      | move cursor to the end of the file                             |
| `Shift+a`      | move cursor to the end of the line and go into edit mode       |
| `Shift+v`      | switch to visual mode                                          |
| `dd`           | delete current (selected) line/lines (cut)                     |
| `yy`           | copy current (selected) line/lines                             |
| `p`            | paste from clipboard (internal vim clipboard)                  |
| `/`            | start typing search phrase                                     |
| `n`            | next search result                                             |
| `Shift+n`      | previous search result                                         |
| `^`            | move cursor to beginning of line                               |
| `$`            | move cursor to end of line                                     |
| `Ctrl+b`       | move one screen back                                           |
| `Ctrl+f`       | move one screen forward                                        |
| `mа`           | create new bookmark with name 'a'                              |
| `'a`           | move to bookmark 'a'                                           |

## Windows

| Command                 | Description                     |
|-------------------------|---------------------------------|
| `ctrl+w s`              | split window horizontally       |
| `ctrl+w v`              | split window vertically         |
| `ctrl+w <movement_key>` | move to window                  |
| `ctrl+w K`              | move current window to top      |
| `ctrl+w` _              | maximize size of current window |
| `ctrl+w = `             | align all windows               |

## Tabs

| Command                 | Description               |
|-------------------------|---------------------------|
| `:tabnew [filename]`    | open new tab              |
| `:tabf pat*ern`         | open new tab by pattern   |
| `:tabs`                 | list opened tabs          |
| `gt или :tabn`          | next tab                  |
| `g Shift+t или :tabp`   | previous tab              |
| `:tabfirst или :tabfir` | first tab                 |
| `:tablast`              | last tab                  |
| `:tabm n`               | move tab to n (from 0)    |
| `:tabdo command`        | apply command to all tabs |

## Useful links

* To learn vim you can use built-in tutorial: `vimtutor`
* [Vimium](https://vimium.github.io/)
* [VIM awesome](http://vimawesome.com/)

## Config for .vimrc

### Use 4 spaces instead of tab

Add to file `~/.vimrc`:
```
set tabstop=4
" when indenting with '>', use 4 spaces width
set shiftwidth=4
" On pressing tab, insert 4 spaces
set expandtab
```

### Use arrows to move through document

Add to file `~/.vimrc`:
```
:set nocompatible
```

*I warn you that using arrows to navigate in VIM is a bad manner, because of 
ten-finger print (you have to remove your right hand from its usual position),
speed slows down etc. (google it yourself)*

### Other

* Show line numbers: `set number` 
* Highlight search: `set hlsearch`
* Ignore case match in search: `set ignorecase`
* Dynamically highlight search on typing: `set incsearch`
* Always show status row: `set laststatus=2`
* Always show file title: `set title`

### Indent settings

It could be a little bit annoying while editing some files (e.g. yaml) [vim will autoindent your file](https://stackoverflow.com/questions/51059357/vim-wrong-indent-when-comment-lines-of-yaml-file).

Add this to your .vimrc file to disable auto-indent when typing # (hash) in Yaml files and set Tab and auto-indent to 2 spaces for yaml files
```
autocmd Filetype yaml setlocal indentkeys-=0# tabstop=2 shiftwidth=2
```

To debug your current indent settings use this command:
```
:verbose set autoindent? smartindent? cindent? cinkeys? indentexpr?
```

read more about this [here](http://vimdoc.sourceforge.net/htmldoc/options.html#:set-verbose) and [here](https://unix.stackexchange.com/questions/106526/stop-vim-from-messing-up-my-indentation-on-comments)

### Enable .vimrc for sudo

Best practice is to use `sudoedit` instead of `sudo vim`. You should be doing that anyway. Make sure your `EDITOR` environment variable is set to `vim` (probably already is, or vim is the default; you can set it in your .profile analog if need be).
* You can check current `EDITOR` value by this command: `echo $EDITOR`
* To set `EDITOR` value: `export EDITOR='vim'`

### Set Vim as default editor

To set vim as editor by default - add the following line to the `~/.bashrc` file: `export EDITOR='vim'`

## License

* MIT 2022
* based on [zualex repo](https://github.com/zualex/vim-cheat-sheet)
