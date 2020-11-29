## The vi Editor
For editing files in UNIX system, we usually use the vi editor. Like any other editor it uses internal commands to navigate.
To invoke vi editor just write in terminal:vi filename

### Modes in vi Editor
1. **Command Mode** - The default mode of the editor where every key pressed is interpreted as a command to run.

2. **Input Mode** - Every key pressed after switching to this mode actually shows up as text.

*The Input mode commands are:*


| Command | Function |
| -| -|
| i | Inserts text to left of the cursor |
| a | Appends text to right of the cursor |
| I | Inserts text at the beginning of the line |
| A | Appends text at the end of line |
| o | Opens line below |
| O | Opens line above |
| r*ch* | Replaces single character under cursor with *ch* |
| R | Replaces text from cursor to right (Existing text overwritten) |
| s | Replaces single character under cursor with any number of characters |
| S | Replaces entire line |

3. **ex Mode** - The mode is used to handle files and perform substitution. Pressing a : in the Command Mode invokes this mode.

*Save and exit commands of the ex Mode:*


|Command | Action |
| -| -|
| :w | Saves file and remains in editing mode |
| :x | Saves file and quits editing mode |
| :wq | Saves file and quits editing mode |
| :w n2w.pl | Like Save As in Microsoft Windows |
| :w n2w.pl | As above but overwrites the existing file |
| :q | Quits editing mode when no changes are amde to file |
| :q! | Quits editing mode after abondoning changes |
| :n1,n2w build.sql | Writes lines n1 to n2 to file build.sql |
| :.w build.sql | Writes current line to file build.sql |
| :$w build.sql | Writes last line to file build.sql |
| :!cmd | Runs cmd command and returns to Command Mode |
| :sh | Escapes to UNIX Shell |
| :recover | Recovers the file from a crash |

### Navigation in vi Editor

##### Movement in 4 directions 

- k -> Moves the cursor up
- j -> Moves the cursor down 
- h -> Moves the cursor left 
- l -> Moves the cursor right

##### Word Navigation 
- b -> Moves back to biginning of word
- e -> Moves forward to end of word 
- w -> Moves forward to beginning of word 
