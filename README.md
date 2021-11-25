# vim\_mouse\_2.ahk
AutoHotkey script with Vim (and now also WASD!) bindings to control the mouse with the keyboard

## Modes of Input
Like Vim, vim\_mouse has modes of input, with "Insert mode" acting like a regular keyboard
and "Normal mode" intercepting keys to move and control the mouse instead.

`Win Alt n` enters Normal mode
`Insert` or `Win Alt i` enters Insert mode

### Normal mode

- `hjkl` move the mouse
- `HJKL` jump to edges of the screen
- `M` jump to center of the screen
- `i` left click
- `o` right click
- `p` middle click
- `v` hold down left click
- `V` hold down right click (???)
- `e,0,]` scroll down
- `y,9,[` scroll up
- `d,}` scroll down faster
- `u,{` scroll up faster
- `Y` "yank" a window (reposition it) (press i to release)
- `b` "back" mouse button
- `n` "forward" mouse button
- `Insert,Win+Alt+i` enter Insert mode

### Normal "WASD" mode

You can also use the WASD keys if they're more natural to you than vim movement keys. Switch into
and out of WASD mode with `Win Alt r`

WASD mode is now the default for Normal mode.

- `wasd` move the mouse
- `WASD` jump to edges of the screen
- `C` jump to center the screen
- `r` left click
- `t` right click
- `y` middle click
- `e` scroll down
- `q` scroll up

Note that this necessarily unbinds `d` `e` and `y` from their Vim bindings.

Otherwise, it is just a variant of Normal mode and the rest of the hotkeys remain unchanged.

### Insert mode

Acts like a normal keyboard.

`Win Alt n` puts you in Normal mode.

### Normal "Quick" mode
If you're in persistent Insert mode and just need the mouse keys for a second, you can hold
down Capslock to enter Normal "Quick" mode, which has all the same hotkeys as Normal mode and
ends when Capslock is released.

### Insert "Quick" mode
To quickly edit some text then return to Normal mode, a "quick" mode is also available for Insert.
Great for typing into an address bar or a form field. `Capslock` toggles between Normal and quick
Insert mode.

##### Entering
From Normal mode
- `:` enter QI (Quick Insert mode)
- `Capslock` toggle between QI and Normal mode
- `f` send f then enter QI (for Vimium hotlinks)
- `^f` send ctrl f then enter QI (commonly "search")
- `^t` send ctrl t then enter QI (new tab in the browser)
- `Delete` send Delete then enter QI (for quick fixes)

##### Exiting
From quick Insert mode:
- `^c` exit to Normal mode
- `Enter` send Enter then exit to Normal mode
- `Capslock` toggle between Quick Insert and Normal mode

## The mouse moves too fast! (or too slow)

At the top of the file, mouse speed is controlled by two global variables, FORCE and RESISTANCE.
FORCE controls acceleration and RESISTANCE causes diminishing returns and implicitly creates a
terminal velocity.
