# Ex.No: 5   Logic Programming – Factorial of number   
### Date:
### Register number:212221220026 
### AIM: 
To  write  a logic program for finding the factorial of given number using SWI-PROLOG. 
### ALGORITHM:
1. Start the program
2. Write a rules for finding factorial of given program in SWI-PROLOG.
3. Factorial of 0 is 1 => written as factorial(0,1).
4. Factorial of number greater than 0 obtained by recursively calling the factorial    function.
5. Run the program  to find answer of  query.
6. Stop the program.

### PROGRAM:
```
factorial(0,1).
factorial(A,B) :-  
           A > 0, 
           C is A-1,
           factorial(C,D),
           B is A*D.

```



### OUTPUT:

![Screenshot 2024-03-09 155245](https://github.com/KATHIR1611/AI_Lab_2023-24/assets/128135186/fb48d0bd-10c0-4bec-8c8a-f1f7ba26e12e)


### RESULT:
Thus the factorial of given number was found by logic programming. 
