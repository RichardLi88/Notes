
## VS Code

| Shortcut name             | Control                 |
| ------------------------- | ----------------------- |
| Primary Sidebar           | Ctrl + B                |
| Secondary Sidebar         | Ctrl + Alt + B          |
| Panel/Integrated Terminal | Ctrl + J                |
| Search                    | Ctrl + F                |
| Find all similar words    | Ctrl + D                |
| Close file                | Ctrl + W                |
| Extension                 | Ctrl + Shift + X        |
| Version Control           | Ctrl + Shift + G        |
| Delete Line               | Ctrl + Shift + K        |
| Select Line               | Ctrl + L                |
| Copy line down            | Alt + Shift + DownArrow |

## Vim


#### Editing in visual mode

| Shortcut name       | Control                                                    |
| ------------------- | ---------------------------------------------------------- |
| h,j,k,l             | move left,down,up,right                                    |
| x (in visual mode)  | delete character                                           |
| dw (in visual mode) | deletes word (starts from cursor)                          |
| i                   | insert at cursor (before)                                  |
| a                   | insert at cursor (after)                                   |
| A                   | append to end of line                                      |
| d$                  | delete to end of line (from cursor)                        |
| dd                  | delete entire line                                         |
| u                   | undo                                                       |
| U                   | undo's everything for the whole line                       |
| Ctrl + r            | undo the undo's                                            |
| p                   | put's deleted/copied text below the cursor                 |
| P                   | put's deleted/copied text above the cursor                 |
| rx                  | replace the character with x                               |
| ce                  | deletes the word starting at cursor and enters editor mode |
| o                   | places cursor into editor mode in the line below           |
| O                   | places cursor into editor mode in the line above           |
| R                   | enters replace mode                                        |
| b                   | goes back to previous word (start)                         |
| ge                  | goes back to previous word (end)                           |
| .                   | goes down 10 lines                                         |
|                     |                                                            |


#### Motion
- motions are often combined with operators

| Shortcut name | Control                                                            |
| ------------- | ------------------------------------------------------------------ |
| w             | moves to the start of the next word, EXCLUDING its first character |
| e             | moves to the end of the current word INCLUDING last character      |
| 2w or 2e      | moves across 2 words (to start or end)                             |
| $             | moves to the end of the line INCLUDING last character              |
| 0             | moves to the start of the line EXCLUDING first character           |
#### Other movement / Searches

| Shortcut name     | Control                                                         |
| ----------------- | --------------------------------------------------------------- |
| G                 | moves to end of file                                            |
| gg                | moves to start of file                                          |
| 100 G             | moves to line 100                                               |
| Ctrl + G          | shows which line you are on                                     |
| /                 | lets you search the file in forwards direction                  |
| n                 | (after searching for word) next match of same phrase (down)     |
| N                 | (after searching for word) previous match of same phrase (up)   |
| ?                 | Searches for phrase in backwards direction                      |
| Ctrl + o          | goes back to where you came from before search                  |
| Ctrl + i          | goes further                                                    |
| %                 | place on any parenthesis and will find the matching parenthesis |
| :s/word/newWord/g | substitutes word for new word globally for the line             |
| :#,#/old/new/g    | substitutes old for new globally between line # and #           |
| :%s/old/new/g     | changes old for new for the whole file                          |
#### Command (and Set)

| Shortcut name | Control                                                            |
| ------------- | ------------------------------------------------------------------ |
| :! command    | can execute any command as if it is in terminal                    |
| :w filename   | writes current file to filename                                    |
| :r filename   | retrieves disk file FILENAME and puts it below the cursor position |
| :set ic       | set ignore case (can set to don't ignore case with :set noic)      |
| :set hls is   | hlsearch (highlight search) and incsearch                          |
| /word\c       | ignores case for next command (searching for word)                 |
#### Copy Paste
- can you y as an operator e.g. yw or y$ to copy one word or rest of the line

| Shortcut name | Control                 |
| ------------- | ----------------------- |
| v             | visual mode (highlight) |
| y             | copy (yank)             |
| p             | paste (put)             |
#### Help

| Shortcut name      | Control               |
| ------------------ | --------------------- |
| :help w            | help for w            |
| :help insert-index | help for insert index |
| :help user-manual  | help user manual      |
#### More

| Shortcut name | What it does                    |
| ------------- | ------------------------------- |
| zz            | centre line to middle of screen |
|               |                                 |

## Custom Neovim

| Shortcut        | Function              |
| --------------- | --------------------- |
| Ctrl + [        | Toggle Neotree        |
| gc (in visual)  | comment out a section |
| Alt + Shift + r | replace inside quotes |
#### Telescope (Fuzzy finder)

| Shortcut    | Function            |
| ----------- | ------------------- |
| Space + f,f | fuzzy find files    |
| Space + f,g | Telescope live grep |
| Space + fb  | Telescope buffers   |
| Space +fh   | Telescope help tags |

## Linux Terminal

| Command        | Usage            | Extra Flags          |
| -------------- | ---------------- | -------------------- |
| mkdir          | make directory   |                      |
| rmdir          | remove directory |                      |
| touch filename | create file      |                      |
| rm filename    | remove file      | -rf: recursive force |
| ls             | list files       |                      |
|                |                  |                      |

## Kitty Shortcuts

#### Creating Terminals and arranging layouts


| Shortcut                       | Usage                         |
| ------------------------------ | ----------------------------- |
| Ctrl + Shift + Enter           | Create new Terminal           |
| Ctrl + Shift + Number          | switches to tab number        |
| Ctrl + Shift + [ or ]          | switches to previous/next tab |
| Ctrl + Shift + t               | create new tab for terminal   |
| Ctrl + Shift + left/rightArrow | switches between tabs         |
| Ctrl + Shift + Layout          | Switch layout                 |
| Ctrl + Shift + o               | new tab                       |
| tab                            | switch tab                    |
## Ubuntu Shortcuts (Custom)

| Shortcut               | Usage             |
| ---------------------- | ----------------- |
| Ctrl + Alt + t         | Open new terminal |
| Ctrl + Alt + o         | Open Obsidian     |
| Ctrl + Alt + b         | Open Brave        |
| Ctrl + Shift + Alt + P | poweroff          |
| Ctrl + Shift + Alt + S | Sign Out          |
