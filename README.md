On german keyboards, I like to remap these keys:

```
ö => Enter
ü => Up
ä => Down
```

Having return, up and down right at your fingertips
is nicely convenient.

Edit ``` /usr/share/X11/xkb/symbols/de ``` and replace

``` key <AC10>	{ [odiaeresis, Odiaeresis, dead_doubleacute, dead_belowdot ] }; ```  
with  
``` key <AC10>	{ [ Return, Return ] }; ```

``` key <AD11>	{ [udiaeresis, Udiaeresis, dead_diaeresis, dead_abovering ] }; ```  
with  
``` key <AD11>	{ [ Up, Up ] }; ```

``` key <AC11>	{ [adiaeresis, Adiaeresis, dead_circumflex, dead_caron ] }; ```  
with  
``` key <AC11>	{ [ Down, Down ] }; ```

And then to clear the XKB cache:
```
rm -rf /var/lib/xkb/*
setxkbmap de
```

---

I also tried to achive this via xmodmap. That would have
the benefit that one does not have to edit a system file
and can simply use a script:

```
xmodmap -e "keycode 47 = Return" # ö => Enter
xmodmap -e "keycode 34 = Up"     # ü => Up
xmodmap -e "keycode 48 = Down"   # ä => Down
```

These settings will be gone after a restart.
To reset them manually, run: ``` setxkbmap ```.

To make the mappings permanent, you can put them in a login-script.

But the problem with the above approach is that it gets lost every
time the keyboard changes or sleeps/wakes.
