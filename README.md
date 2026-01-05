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
