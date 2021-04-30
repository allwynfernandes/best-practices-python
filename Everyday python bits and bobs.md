# Handy Best practices for Python
A list of quick tips that vastly improve your code.

Courtesy: CoreyMS.com; 


#### Use (help) to find out available functions within a module
```
# To learn more about a module use help()
help(time)
# To find out the attributes and methods available with a function use dir()
dir(time)

```

#### Use with instead of open and close
```python
# Before
f = open('somefile.txt')
file = f.read()
f.close()

# After
with open('somefile.txt')
	file = f.read()
```
Note: Works with any file, sql database connections, resources in general.


#### Use getpass instead of input for accepting sensitive information
```python
from getpass import getpass
username = input("Username: ")
password = getpass("Password: ")
print("Logging in...")

```


#### Use Enumerate instead of for loops to increment/show the index
```python
# Before
things = ['bat', 'ball', 'car', 'table']
index = 0
for item in things:
	print(index, item)
	index += 1
	
# After 
for index, item in enumerate(things):
	print(index, item)
```
Note: Notice how clean it looks. You could also give enumerate a start position like 1 or some other number to start at.

#### Use Zip instead of enumerate
It lets you loop over two lists at once.
```python
things = ['bat', 'ball', 'car', 'table']
colors = ['red', 'green', 'blue', 'yellow']

for item, color in zip(things, colors):
	print(f"I have a {color} color {item}")
```
Note: Zip actually returns a tuple which we are unpacking here into individual elements. You can add as many lists to the zip as you like. If you have lists of varying lengths, the looping stops on the shortest list.


#### Use classes and attributes
Using setattr lets you set variables as attributes
```python
# Before
class Character_Template():
	pass
	
monster = Character_Template()

monster.name = "Madmax"
monster.health = 500
monster.attack = 200

# After

class Character_Template():
	pass
monster = Character_Template()
powers = ['water', 'fire', 'wind']

setattr(monster, 'name', 'Madmax')
setattr(monster, 'health', 500)
setattr(monster, powers)

# Extra: This gets the monster's name
getattr(monster, 'name')
```
 



#### Use  execution context to decide flow
Useful for differentiating when importing vs executing a python script.
If a `__main__` is not used, the code in a script would run right away every time it is imported.
If you want the script to run only when executed from terminal but not when imported, use `__main__`.
Doing this is incredibly simple. Just add a conditional statement!
```python
print('The script is excuting')

def start_process():
	print('The process is starting')
	# DO Some Task
	print('Process complete')
	
def main():
	start_process()
	print("Running the main process")

if __name__ == "__main__":
	 main()
	print('The processing function has executed from within context')




```
Note: 
When we exclusively set the value of the `__name__` variable as `__main__` means instructing python to say that it is executing your script and not just importing it.
Note: Its best to put the core function of your code (the reason why your script exists) inside the `__main__` block. that way everyone else knows where the program begins execution.





