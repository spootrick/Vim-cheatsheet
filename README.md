# Vimtutor Notes
The basic Vim commands extracted from vimtutor.

## Basic Knowledge
Synax: operator [number] motion

where:
  - operator: is what to do, such as  d  for delete
  - [number]: is an optional count to repeat the motion
  - motion: moves over the text to operate on, such as  w (word), $ (to the end of line), etc.

Some of the operators and motions

| Operator | Description |
| :---: | --- |
| d | Delete the line, word, sentence, ... |
| p | Put previously deleted text after cursor |
| x | Delete character under the cursor |
| r | Replace character under the cursor |
| R | Replace more than one character (Replace mode) |
| c | Change |
| n | Next |
| N | Previous |
| o | Open new line BELOW the cursor and start insert mode |
| O | Open new line ABOVE the cursor and start insert mode |
| a | Append after cursor |
| A | Append at the end of the line |
| y | Yank (copy) |


| Motion | Description |
| :---: | --- |
| w | Until start of the next word, EXCLUDING its first character. |
| e | To the end of the current word, INCLUDING the last character. |
| $ | To the end of the line, INCLUDING the last character. |
| 0 | To move to the start of the line. (zero) |
| gg | To move to the start of the file. |
| G | To move to the end of the file. |


## Deletion
| Command | Memo | Description | Example |
| :---: | --- | --- | --- |
| x | - | delete character under the cursor | - |
| dw | delete word | deletes the word | dw, d2w |
| d$ | regex | delete till end of the line | - |
| dd | - | delete whole line | dd, 2dd |


## Undo Changes
Press `u` to undo last commands, `U` to fix a whole line.  
Press `CTRL+R` to redo. (undo the undo's)

## Cursor Location and File Status
Type `CTRL-G` to show location in the file and the file status. (see `:help ruler`)

## Searching
Type `/` followed by a phrase to search for it. Search from current cursor position to bottom of the file.  
Type `?` followed by a phrase to search for it. This will search backwards.

To search for the same phrase again, type `n`.  
To search for the same phrase in the opposite direction, type `N`.

To go back to where you came from press `CTRL-O`. (Letter o) To go forward press `CTRL-I`

### Matching Parentheses Search
To find a matching ), ] or } type `%` character.

## Substitude (Search and Replace)
Syntax: `:s/old/new/g`

`g` means to substitude globally in the line.  
  - `#,#s/old/new/g` where #,# are the line numbers of the range of lines where the substitution is to be done.
  - `%s/old/new/g` to change every occurrence in the whole file
  - `%s/old/new/gc` to find every occurrence in the whole file, with a prompt whether to substitute or not

## Save as
Type `:w filename`

## Execute External Command
Type `:!` before any shell command. Like `:!ls -lh`

## Visual Mode
Type `v` to select text. You can perform any command on this selected part of text.

## Retrieve and Merge Files
To insert the contents of a file, type `:r filename`  
To insert the contents of an external command output, type `:r !command`

## Set Option
You can set options to vim to use. This commands will be useful and persistent within .vimrc file.  

Syntax: `:set xxx`

For example;
  - `set ignorecase` or `set ic` to disable `set noignorecase`
  - `set hlsearch` or `set hls` to disable `set nohlsearch` to disable highlights `:noh`
  - `set incsearch` or `set is` to disable `set noincsearch`

Can either be used the long or the short option name.

## Command Completion
Press `CTRL-D` and `TAB`  
**Make sure Vim is not in compatible mode `:set nocp`**  
To activate type the start of a command like `:e` and press CTRL-D to see all the commands, press `TAB` to cycle each command.

## Getting Help
Type `:help <command>`  
Press `CTRL-W` to cycle between screens.

