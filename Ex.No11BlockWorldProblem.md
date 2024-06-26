# Ex.No: 11  Planning – Block World Problem 
### Date:                                                                  
### Register number:212221220026 
### AIM: 
To find the sequence of plan for Block word problem using PDDL  
###  ALGORITHM:
1. Start the program <br>
2.Create a domain for Block world Problem <br>
3.Create a domain by specifying predicates clear, on table, on, arm-empty, holding. <br>
4.Specify the actions pickup, putdown, stack and un-stack in Block world problem <br>
5.In pickup action, Robot arm pick the block on table. Precondition is Block is on table and no other block on specified block and arm-hand empty.<br>
6.In putdown action, Robot arm place the block on table. Precondition is robot-arm holding the block.<br>
7.Obtain the plan for given problem.<br> 
     
### PROGRAM:
```
(define (domain blocksworld)
(:requirements :strips :equality)
(:predicates (clear ?x)
 (on-table ?x)
 (arm-empty)
 (holding ?x)
 (on ?x ?y))
(:action pickup
 :parameters (?ob)
 :precondition (and (clear ?ob) (on-table ?ob) (arm-empty))
 :effect (and (holding ?ob) (not (clear ?ob)) (not (on-table ?ob))
 (not (arm-empty))))
(:action putdown
 :parameters (?ob)
 :precondition (and (holding ?ob))
 :effect (and (clear ?ob) (arm-empty) (on-table ?ob)
 (not (holding ?ob))))
(:action stack
 :parameters (?ob ?underob)
 :precondition (and (clear ?underob) (holding ?ob))
 :effect (and (arm-empty) (clear ?ob) (on ?ob ?underob)
 (not (clear ?underob)) (not (holding ?ob))))
(:action unstack
 :parameters (?ob ?underob) 
 :precondition (and (on ?ob ?underob) (clear ?ob) (arm-empty))
 :effect (and (holding ?ob) (clear ?underob)
 (not (on ?ob ?underob)) (not (clear ?ob)) (not (arm-empty)))))
```









### INPUT:
```
(define (problem pb1)
 (:domain blocksworld)
 (:objects a b)
 (:init (on-table a) (on-table b) (clear a) (clear b) (arm-empty))
 (:goal (and (on a b))))
```

### OUTPUT:

![280242688-fafc1299-e36d-424e-aeda-461cc605d215](https://github.com/KATHIR1611/AI_Lab_2023-24/assets/128135186/a385309e-9271-4e25-9491-c9a0e0d94ea7)



### RESULT:
Thus the plan was found for the initial and goal state of block world problem.
