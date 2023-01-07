When you press Alt+Tab it often happens that the mouse pointer is in the center of the screen and occupies an area of windows cycling widget.  
In such cases, you will have simultaneously two highlighted items in the widget. This confusing greatly and very often when you quickly switch between the windows you will select and switch to a wrong window. Solution of the problem is to suppress the item hovering under the mouse cursor.  
Since version 4.14 xfce uses gtk3 library for rendering, to solve the problem we just override css styling for windows cycling widget (tabwin) in the user's gtk3 css config file:  
1. Open or create gtk3 user config file `~/.config/gtk-3.0/gtk.css`
2. Paste into the code snippet:  
```
#xfwm-tabwin button:hover:not(:checked) {
  background: transparent;
  outline-color: transparent;
  border-color: transparent;
  box-shadow: none; }

```
3. Save and reboot
