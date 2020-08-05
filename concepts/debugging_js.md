## Following folow and getting visibility in JavaScript

### Skills Workshop Write Up

In the workshop we covered two (not entirely distinct) concepts to help us (as readers of the code) understand code, most likely with a view to then debug the code as it is not exhibiting the desired behaviour.

Whilst the details of implementing these techniques will be focussed on JavaScript they are concepts that can and should be applied to any code in any programming language, all that changes is the implementation.

The two concepts were:
- Getting visibility
- Following Flow

### Getting Visibility

Getting visibility is the practice of looking at data in the variables in the code we are trying to understand. The actual value of a variable at a point in the code can be checked against the desired/expected value.

Similarly by printing (using ```console.log()```) an object's properties, parameters, and/or the functions return calls, the coder can see what is being actually produced and executed by the code at points of the code at their own choosing, and compare them to what is desired/expected.

A coder could also use ```console.log()``` to print the ```this``` keyword and differing points of the program to find out it's value.


### Following Flow

Generally speaking following the flow refers to the practice of understanding what happens when a piece of code runs. Being able to see what lines of code are being executed, which ones are not, and in what order gives us understanding of the paths of execution the code is implementing.

This can be done in JavaScript by utilising the ```console.log()``` function. A simple but useful way to use this tehcniwue is to have different but recognisable strings logged to the console. A good idea would be printing unique strings on each branch of an if/else statement. From the printed string the coder can discern what branch of the if/else statement was followed.

### Debugging JavaScript

In JavaScript there is a ```debugger``` statement which stops the code during execution at the line where the ```debugger``` statement is, and calls the debugging function (has the program automatically enter the debugging mode) if available.

This debugging mode can also be manually accessed by use of the Developer Tools/inspect function in a a web browser (such as Google Chrome) and clocking the Sources tab. Accessed this way the web browser will need to be refreshed to reload the code.

#### Breakpoints

When inspecting the code that was run by clicking the line number a red dot signifies the creation of a **breakpoint**. The breakpoints (similar to to the debugging statement mentioned above) stop the code at that specific line and allow the User to "step" through the code, offering the chance to exmaine the JavaScript values. Lines of code can have multiple breakpoints along them, which allows for very precise exmaination of the values the code is producing.
