## ${\color{red}Wordpress \ Hooks \ - \ Actions \ and \ Filters}$

**Hooks** - way for one piece of code to interact/modify another piece of code at specific, pre-defined spots. <br> 

There are two types of hooks: Actions and Filters. <br>
To use either, you need to write a custom function known as a Callback, and then register it with a WordPress hook for a specific action or filter.

**Actions** - allow to add data or change how WordPress operates. <br>
Actions will run at a specific point in the execution of WordPress Core, plugins, and themes. <br>
Callback functions for Actions can perform some kind of a task, like echoing output to the user or inserting something into the database. <br>
Callback functions for an Action do not return anything back to the calling Action hook. <br>

**Filters** - give the ability to change data during the execution of WordPress Core, plugins, and themes. <br> 
Callback functions for Filters will accept a variable, modify it, and return it. <br>
They are meant to work in an isolated manner, and should never have side effects such as affecting global variables and output.<br>
Filters expect to have something returned back to them.

WordPress provides many hooks that you can use, but you can also create your own so that other developers can extend and modify your plugin or theme.

**Actions vs. Filters** <br>

Action takes the info it receives, does something with it, and returns nothing. <br>
In other words: it acts on something and then exits, returning nothing back to the calling hook. <br><br>
Filter takes the info it receives, modifies it somehow, and returns it. <br>
In other words: it filters something and passes it back to the hook for further use. <br>

Said another way:

Action interrupts the code flow to do something, and then returns back to the normal flow without modifying anything. <br>
Filter is used to modify something in a specific way so that the modification is then used by code later on.
