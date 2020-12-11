## The vi Editor

For editing files in UNIX system, we usually use the vi editor. Like any other editor it uses internal commands to navigate.
To invoke vi editor just write in terminal:vi filename

### Modes in vi Editor

1. **Command Mode** - The default mode of the editor where every key pressed is interpreted as a command to run.

2. **Input Mode** - Every key pressed after switching to this mode actually shows up as text.

_The Input mode commands are:_

| Command | Function                                                             |
| ------- | -------------------------------------------------------------------- |
| i       | Inserts text to left of the cursor                                   |
| a       | Appends text to right of the cursor                                  |
| I       | Inserts text at the beginning of the line                            |
| A       | Appends text at the end of line                                      |
| o       | Opens line below                                                     |
| O       | Opens line above                                                     |
| r*ch*   | Replaces single character under cursor with _ch_                     |
| R       | Replaces text from cursor to right (Existing text overwritten)       |
| s       | Replaces single character under cursor with any number of characters |
| S       | Replaces entire line                                                 |

3. **ex Mode** - The mode is used to handle files and perform substitution. Pressing a : in the Command Mode invokes this mode.

_Save and exit commands of the ex Mode:_

| Command           | Action                                              |
| ----------------- | --------------------------------------------------- |
| :w                | Saves file and remains in editing mode              |
| :x                | Saves file and quits editing mode                   |
| :wq               | Saves file and quits editing mode                   |
| :w n2w.pl         | Like Save As in Microsoft Windows                   |
| :w n2w.pl         | As above but overwrites the existing file           |
| :q                | Quits editing mode when no changes are amde to file |
| :q!               | Quits editing mode after abondoning changes         |
| :n1,n2w build.sql | Writes lines n1 to n2 to file build.sql             |
| :.w build.sql     | Writes current line to file build.sql               |
| :$w build.sql     | Writes last line to file build.sql                  |
| :!cmd             | Runs cmd command and returns to Command Mode        |
| :sh               | Escapes to UNIX Shell                               |
| :recover          | Recovers the file from a crash                      |

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

  _A repeat factor speeds up cursor movement along the line. For example 5b takes the cursor 5 words back._

##### Moving to line extremes (0,| and $)

- In order to move to the first character of the line either use 0(zero) or |.
  | takes the repeat factor and using that you can position the cursor on a certain column.

- In order to move to the end of current line we use $.

##### Scrolling ([Ctrl-f],[Ctrl-b],[Ctrl-d] and [Ctrl-u])

Faster movement can be achieved by scrolling text in the window using the control keys ->

- [Ctrl-f] Scrolls forward
- [Ctrl-b] Scrolls backward
- [Ctrl-d] Scrolls half page forward
- [Ctrl-u] Scrolls half page backward

### Editing Text in vi Editor

##### Deleting Text (x and dd)

The simplest text deletion is achieved with **x** command. This command deletes the character under the cursor.
The entire line are removed by **dd** command. Move to the cursor on any line and press dd.

##### Moving Text (p)

Put the text at new location with **p or P**.
Note-> _p and P place text on right and left only when you delte parts of lines. But the same keys get associated with "below" and "above" when you delete complete lines._

##### Copying Text (y and p)

vi editor uses the term **yanking** for copying the text. For copying one or more lines we use the command **yy**.

##### Joining Lines (J)

In word processors, you join the current and next line by moving the cursor to the end of the line and pressing [Delete]. This technique won't work in vi-editor. For this we use the command **J**.

##### Undoing the last editing instructions (u and U)

vi ditor provides the command **u** to undo the last change made.
Note-> 1. _Must use **u** in the command mode._ 2. _When the number of editing changes have been made to a single line, vi allows you to discard such changes before you move away from that line using the command **U**._

### Reapeating the last command (.)

vi editor provides you the facility to repeat the command used previously. The **.(dot)** command is used for repeating both in Input and Command mode. The principle is : Use the actual command once and then repeat it other placs by using the dot command.
The . command can be used to repeat only the most recent editing operations (be it insertion,deletion or any other that modifies the buffer). This doesn't include search or navigation commands.
