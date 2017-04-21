## Triggering Function Calls with Buttons

In the scenario below, a single button has been wired to pin 17.

![4-pin-btn](4-pin-btn.png)

You can use the button to call functions that take no arguments.

1. First you need to set up the button using Python 3

	~~~python
	from gpiozero import Button
	btn = Button(17)
	~~~

1. Next you need to create a callable function that has no arguments

	~~~python
	def hello():
		print('Hello')
	~~~

1. Lastly the trigger can be created.

   ~~~python
   btn.when_pressed = hello
   ~~~
   
1. Now each time the button is pressed, you should see `Hello` being printed to the Python shell. The function can be as complex as you like, or you can even call functions that are parts of modules. Like this example, that would switch on an LED on pin 4.

~~~python
from gpiozero import Button, LED

btn = Button(17)
led = LED(4)

btn.when_pressed = led.on
