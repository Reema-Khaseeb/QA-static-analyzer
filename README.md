# Static Analyzer

<br/>

## Unreachable Code cases:

* **False condition (if False)**
if the condition in if-statement is 'False' keyword, then it'll never be excecuted that causes Unreachable code warening
##### Code Explanation:
###### if the line contains 'if' then it's if-statement, check the condition, if it's 'False' keyword, then the blocks inside that conditon won't be excecuted and unreachable


* **True condition (if)**
if the condition in if-statement is 'True' keyword that is always excecuted, then else-statement will never be excecuted that causes Unreachable code warening

##### Code Explanation:
###### if the line contains 'if' then it's if-statement, check the condition, if it's 'True' keyword, then walk through the lines from that line until the next function, when encounter else-statement, then that line and the blocks inside it won't be excecuted and unreachable


* **After return statement**
When return statement is excecuted, it terminates the function call, therefore any line or line comes after return statement inside that function, it won't be excecuted, causing Unreachable code warening

##### Code Explanation:
###### if the line contains 'return' , check the next lines, if they're neither else-statement nor definition of a new function, besides not an empty lines, then they will never run they're unreachable


* **Same condition in if and else statement**
##### Code Explanation:
###### if the line contains 'if' then it's if-statement, store the condition in a varable by removing any leading and trailing spaces, ':', and 'if'. And look for 'elif' condition if found, store its condition in another variable. Now compare both conditions of if-statement and elif-statement, if they're the same, the elif condition will never run as the same condition in if-statement has already been handled



