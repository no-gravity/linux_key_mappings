On german keyboards, I like to remap these keys:

```
xmodmap -e "keycode 47 = Return" # ö => Enter
xmodmap -e "keycode 34 = Up"     # ü => Up
xmodmap -e "keycode 48 = Down"   # ä => Down
```

Having return, up and down right at your fingertips
is nicely convenient.

These settings will be gone after a restart.
To reset them manually, run: ``` setxkbmap ```.

To make the mappings permanent, you can put them in a login-script.

An alternative might be the ``` input-remapper ``` command.
I have not tried it yet.

Problem with the above approach is that it gets lost every
time the keyboard changes or sleeps/wakes.

An alternative that survives keyboard changes:

Edit ``` /usr/share/X11/xkb/symbols/de ``` and replace

``` key <AC10>	{ [odiaeresis, Odiaeresis, dead_doubleacute, dead_belowdot ] }; ```  
with  
``` key <AC10>	{ [ Return, Return ] }; ```

``` key <AD11>	{ [udiaeresis, Udiaeresis, dead_diaeresis, dead_abovering ] }; ```  
with  
``` key <AD11>	{ [ Up, Up ] }; ```



And then to clear the XKB cache:
```
rm -rf /var/lib/xkb/*
setxkbmap de
```
