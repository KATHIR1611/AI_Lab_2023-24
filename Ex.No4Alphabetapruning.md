# Ex.No: 4   Implementation of Alpha Beta Pruning 
### Date:02/03/2024                                                                            
### Register number:212221220026 
### AIM: 
Write a Alpha beta pruning algorithm to find the optimal value of MAX Player from the given graph.
### ALGORITHM:
1. Start the program
2. Initially  assign MAX and MIN value as 1000 and -1000.
3.  If maximum depth is reached then return the score value of leaf node. [depth taken as 3]
4.  In Max player turn, assign the alpha value by finding the maximum value by calling the minmax function recursively.
5.  In Min player turn, assign beta value by finding the minimum value by calling the minmax function recursively.
6.  Print the best value of Max player.
7.  Stop the program. 

### PROGRAM:
```
MAX, MIN = 1000, -1000
 
def minimax(depth, nodeIndex, maximizingPlayer,
            values, alpha, beta):
  
    if depth == 3:
        return values[nodeIndex]
 
    if maximizingPlayer:
      
        best = MIN
 
        for i in range(0, 2):
             
            val = minimax(depth + 1, nodeIndex * 2 + i,
                          False, values, alpha, beta)
            best = max(best, val)
            alpha = max(alpha, best)
 
            if beta <= alpha:
                break
          
        return best
      
    else:
        best = MAX
 
       
        for i in range(0, 2):
          
            val = minimax(depth + 1, nodeIndex * 2 + i,
                            True, values, alpha, beta)
            best = min(best, val)
            beta = min(beta, best)
 
      
            if beta <= alpha:
                break
          
        return best
      
values = [3, 5, 6, 9, 1, 2, 0, -1] 
print("The optimal value is:", minimax(0, 0, True, values, MIN, MAX))
```

### OUTPUT:

![Screenshot 2024-02-25 154337](https://github.com/KATHIR1611/AI_Lab_2023-24/assets/128135186/ded4cbdb-b8d2-44e2-b045-86bfe72f73bc)



### RESULT:
Thus the best score of max player was found using Alpha Beta Pruning.
