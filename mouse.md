# Default behaviors when using X11

Last mouse scroll will be somehow carried over to another app when you switch to it

Example:
> 1. Scroll down 4 steps in browser
> 2. ALT+TAB to switch to VSCode
> 3. Scroll up 1 step
> 4. Ended up at position as if I scrolled down 3 steps

# Solution

## Install imwheel

```sh
sudo apt install imwheel
# activate imwheel after installing, add imwheel to startup apps
imwheel
```

## Immediate results

"Scroll got carried over" is gone, but most mouse button functions stopped working

## Final fix

Create `~/.imwheelrc` with your custom key maps

```txt
".+"
None,      Up,   Button4, 1
None,      Down, Button5, 1
Control_L, Up,   Control_L|Button4
Control_L, Down, Control_L|Button5
None, Thumb1, Alt_L|Left
None, Thumb2, Alt_L|Right
```

### Explanations

symbol|meaning
-|-
`".*"`|apply below setting to all applications
`None, Up, Button4, 1`|Map `Scroll Up` to `Press Button_4 1 time`
`None, Down, Button5, 1`|Map `Scroll Down` to `Press Button_5 1 time`
`Control_L, Up, Control_L\|Button4`|Map `Ctrl_L + Scroll Up` to `Ctrl_L + Button_4`
`Control_L, Down, Control_L\|Button5`|Map `Ctrl_L + Scroll Down` to `Ctrl_L + Button_5`
`None, Thumb1, Alt_L\|Left`|Map Backward button to Alt_L+Left
`None, Thumb2, Alt_L\|Right`|Map Forward button to Alt_L+Right
