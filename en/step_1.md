- In the diagram below, a single button has been wired to pin 17.

![4-pin-btn](images/4-pin-btn.png)

- You can use the button to call functions that take no arguments:

- First you need to set up the button using Python 3 and the `gpiozero` module.

	```python
	from gpiozero import Button
	btn = Button(17)
	```

- Next you need to create a function that has no arguments. This simple function will just print the word `Hello` to the shell.

	```python
	def hello():
		print('Hello')
	```

- Finally, create a trigger that calls the function.

   ```python
   btn.when_pressed = hello
   ```
   
- Now each time the button is pressed, you should see `Hello` being printed to the Python shell. 

- Your function can be as complex as you like - you can even call functions that are parts of modules. In this example, pressing the button switches on an LED on pin 4.

	```python
	from gpiozero import Button, LED

	btn = Button(17)
	led = LED(4)

	btn.when_pressed = led.on
	```

