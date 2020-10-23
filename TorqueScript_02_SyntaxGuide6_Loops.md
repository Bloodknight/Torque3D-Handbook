# Loops 
As the name implies, this structure type is used to repeat logic in a loop based on an expression. The expression is usually a set of variables that increase by count, or a constant variable changed once a loop has hit a specific point. For Loop

## For Loop
**for Loop Syntax:**
```
for(expression0; expression1; expression2) 
{
    statement(s);
}
```
One way to label the expressions in this syntax are (startExpression; testExpression; countExpression). Each expression is separated by a semi-colon.

**Example**:
```cs
for(%count = 0; %count < 3; %count++) 
{
    echo(%count);
}

// OUTPUT:
// 0
// 1
// 2
```
The first expression creates the local variable count and initializing it to 0. In the second expression determines when to stop looping, which is when the count is no longer less than 3. Finally, the third expression increases the count the loop relies on. 




## While Loop
A while loop is a much simpler looping structure compared to a for loop.

**while Loop Syntax:**
```cs
while(expression) 
{
    statements;
}
```
As soon as the expression is met, the while loop will terminate:

**Example**:
```cs
%countLimit = 0;

while(%countLimit <= 5)
{
   echo("Still in loop");
   %countLimit++;
}
echo("Loop was terminated");

// OUPUT:
// Still in loop
// Still in loop
// Still in loop
// Still in loop
// Still in loop
// Still in loop
// Loop was terminated
```