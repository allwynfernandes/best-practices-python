### Code in English
Remember, the first purpose of code is to be understood. First by you, then by future you(or your colleague) and then finally by the computer. Short availibity of time or laziness is no excuse to write sloppy code. You will thank(or curse) yourself years later when you have to come back to a program you wrote a while back. The outcome depends completely on how you wrote your code the first time. Be consise. Make sure you code reads like English, like poetry even.
Here's an example
#### BAD
```py
from time import *
sleep(3)
```
#### Good
```py
import time
time.sleep(3)

```
While this may seem silly at first and on short scripts, it's use shines when the codebase evolves to 1000+ lines. If your code looks like the latter, months later when you come back to this code base, you konw exactly what sleep is and which module it is coming from. Compare that to the anonymous sleep in the former example and you're in for trouble.
It may seem like the second example may take up needless strokes but remember it's not about how many keystrokes you can save. It's also about readibility. 


### DRY
Do Not Repeat yourself. Nobody enjoys listening to a broken record. No human I know enjoys doing repetitive, mundane tasks, again and again and aging... It is soul crushing and that's what we want to avoid while programming. Hence, DRY. Instead of doing the same thing 3 times, throw those lines of code into its own fuction. It will serve you well to both debug as well as refactor, edit, update and read the code.

```py

def print_silly():
    print("this new thing")
    print ("but then there is also this thing")
    print("something new will soon be added")

def main():
    for i in range(3):
        print_silly()

# This program will print the statement 9 times
main()

```