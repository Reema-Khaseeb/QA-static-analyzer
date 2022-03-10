# Static Analyzer Tool Project 
Supervisor: Doc. Mustafa Assaf <br>
(Team 12) Members: 
* Reema Khaseeb - 11924143
* Yara Abu-Odeh - 11926410
* Zubaida Sadder - 11925174 <br>

Written in Python. <br>
11 - March - 2022 <br>
## Description:
This project reads a text file that contains a code in Python. It analysis it based on the following: 
- Magic Number
- Division by zero 
- Number of parameters
- Unreachable code.

The code in the text file have different issues from the all of the above cases. <br>
**NOTES When writing the code :**
1. Add a space between operations (e.g: x == 10)
2. Add a space before colomns (e.g function definitons: def foo(1,2,3) : ) 
<br/>

## DEMO Video: 
[Team 12 demo video link](https://drive.google.com/file/d/1DevhtQpl219bwaLXx7vYtl6GGcWoWSS9/view?usp=sharing)

## General Functions 
* `read_func` : Reads the text file line by line 
* `functions_lines` :  It finds the indicies of the lines.
* `find`: It finds a specific string, or a specific line that contains the string.
* `split_by`: Splits strings and return them in a list. 

## Magic Number
We considered the occurance of a magic number after valued in this list ['>', '<', '==','!=', '** ','+', '-', '/','*', 'return'] . <br>
`magic_num` function checks if there exist a number after one of the values from the list. 

## Division by zero
Division by zero happens when a value is devided by 0 integer or a variable equals to zero. using `DividByZero` function.

## Number of parameters
When writing functions, the maximum number of parameters is 3. so `parameters_number` function checks the number of parameters in each function in the code. <br> 
Functions appears either in definition or when its called for execution. <br>
These two cases are handeled in `parameters_number(filename)` that reads the whole code searching for functions names. <br>
After finding the function, `get_parameters(func)` is used to put the parameters in a list and then count & check them using `len_parameters(pars,location)` function that prints the error msg as well. 

## Unreachable Code cases:

* **False condition (if False)** <br/>
if the condition in if-statement is 'False' keyword, then it'll never be excecuted that causes Unreachable code warening
##### Code Explanation:
###### if the line contains 'if' then it's if-statement, check the condition, if it's 'False' keyword, then the blocks inside that conditon won't be excecuted and unreachable

<br/><br/>
* **True condition (if)** <br/>
if the condition in if-statement is 'True' keyword that is always excecuted, then else-statement will never be excecuted that causes Unreachable code warening

##### Code Explanation:
###### if the line contains 'if' then it's if-statement, check the condition, if it's 'True' keyword, then walk through the lines from that line until the next function, when encounter else-statement, then that line and the blocks inside it won't be excecuted and unreachable

<br/><br/>
* **After return statement** <br/>
When return statement is excecuted, it terminates the function call, therefore any line or line comes after return statement inside that function, it won't be excecuted, causing Unreachable code warening

##### Code Explanation:
###### if the line contains 'return' , check the next lines, if they're neither else-statement nor definition of a new function, besides not an empty lines, then they will never run they're unreachable

<br/><br/>
* **Same condition in if and else statement**  <br/>
##### Code Explanation:
###### if the line contains 'if' then it's if-statement, store the condition in a varable by removing any leading and trailing spaces, ':', and 'if'. And look for 'elif' condition if found, store its condition in another variable. Now compare both conditions of if-statement and elif-statement, if they're the same, the elif condition will never run as the same condition in if-statement has already been handled



