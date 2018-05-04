# Regular Expressions

Find regexes that match the following. (e.g. find a single regex that matches
both `antelope` and `antelopes`.)

* Single regex that matches either of these:

    antelope rocks out
    
    antelopes rock out

### ANSWER:
`/antelopes?\srocks?\sout/`


* Regex that matches either of:

    goat
    
    moat

  but not:

    boat

### ANSWER:
`/[gm]oat/`


* Regex that matches dates in YYYY-MM-DD format. (Year can be 1-4 digits, and
  month and day can each be 1-2 digits). This does not need to verify the date
  is correct (e.g 3333-33-33 can match).

  2000-10-12

  1999-1-20

  1999-01-20

  812-2-10

### ANSWER:
`/\d){4}-\d{1,2}-\d{1,2}/`


## State Machine

 * Draw a state machine that corresponds to the following regex:

      `ab*c+d?[ef]`

### ANSWER:
See attached .png file.


* A lion can be sleeping, eating, hunting, or preening. Draw a state
  machine diagram for the lion and label the transition events that
  cause state transitions.

### ANSWER:
See attached .png file.


* The VT-100 terminal (console) outputs text to the screen as it
  receives it over the wire. One exception is that when it receives an
  ESC character (ASCII 27), it goes into a special mode where it looks
  for commands to change its behavior. For example:

      ESC[12;45f

  moves the cursor to line 12, column 45.

      ESC[1m

  changes the font to bold.

  * Come up with regexes for the two above sequences. The one to set the
    cursor position should accept any digits for the row and column. The
    bold sequence need only accept `1` (and is a trivial regex). (ESC is
    a single character which can be represented with `\e` in the regex.)

### ANSWER:
  * `^\e\[\d+;\d+f$`
  * `^\e\[1m$`

  * Draw a state machine diagram for a VT-100 that can consume regular
    character sequences as well as the two above ESC sequences.


# Algorithms

### Excercise I

 * a: O(n)
 * b: O(log n)
 * c: O(log n)
 * d: O(n)
 * e: O(n^3)
 * f: O(n)
 * g: O(n)
 
### Excercise II

* a:

  ``` 
    function maxDiff(array) {
      array.sort((a, b) => b - a);
      return array[0] - array[array.length - 1];
    }
```

* b: Use a binary search sort. I.e. start with n/2
    ```
    Start with f = n/2
      keep track of last attempt (i.e. broke/didn't break)
      if egg breaks try f = f/2 
      else try f = n - ( f/2 )
    Keep going until you find state change from broken to not broken and you can't halve the floors anymore
    ```
