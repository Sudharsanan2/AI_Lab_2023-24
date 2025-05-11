# Ex.No: 10  Logic Programming –  Simple queries from facts and rules
### DATE: 24/04/2025                                                                         
### REGISTER NUMBER : 212222060259
### AIM: 
To write a prolog program to find the answer of query. 
###  Algorithm:
 Step 1: Start the program <br> 
 Step 2: Convert the sentence into First order Logic  <br> 
 Step 3:  Convert the sentence into Horn clause form  <br> 
 Step 4: Add rules and predicates in a program   <br> 
 Step 5:  Pass the query to program. <br> 
 Step 6: Prolog interpreter shows the output and return answer. <br> 
 Step 8:  Stop the program.
### Program:

### Task 1:
Construct the FOL representation for the following sentences <br> 
1.	John likes all kinds of food.  <br> 
2.	Apples are food.  <br> 
3.	Chicken is a food.  <br> 
4.	Sue eats everything Bill eats. <br> 
5.	 Bill eats peanuts  <br> 
   Convert into clause form and Prove that John like Apple by using Prolog. <br> 
### Program:

likes(john,X):-

 food(X).
 
eats(bill,X):-

 eats(sue,X).
 
eats(Y,X):-

 food(X).
 
eats(bill,peanuts).

food(apple).

food(chicken).

food(peanuts).

### Output:

![372435471-bda68815-93a1-4930-adac-c285489fbebb2](https://github.com/user-attachments/assets/cab8d0ad-f769-4d99-a9b9-062567b9f4be)

### Task 2:
Consider the following facts and represent them in predicate form: <br>              
1.	Steve likes easy courses. <br> 
2.	Science courses are hard. <br> 
3. All the courses in Have fun department are easy <br> 
4. BK301 is Have fun department course.<br> 
Convert the facts in predicate form to clauses and then prove by resolution: “Steve likes BK301 course”<br> 

### Program:

likes(steve,X):-

 easycourse(X).
 
hard(sciencecourse).

easycourse(X):-

 course(X,dept(havefun)).
 
course(bk301,dept(havefun)).

### Output:

![372436185-c4690939-c5f9-4820-b99e-79cbc047885933](https://github.com/user-attachments/assets/4e3fecd2-9937-4b99-b6a4-79baf45e9ee3)

### Task 3:
Consider the statement <br> 
“This is a crime for an American to sell weapons to hostile nations. The Nano , enemy of America has some missiles and its missiles were sold it by Colonal West who is an American” <br> 
Convert to Clause form and prove west is criminal by using Prolog.<br> 
### Program:

 american(X),

 weapon(Y),
 
 hostile(Z),
 
 sells(X,Y,Z).
 
weapon(Y):-

 missile(Y).
 
hostile(Z):-

 enemy(Z,X).
 
sells(west,Y,nano):-

 missile(Y),
 
 owns(nano,Y).
 
missile(m).

owns(nano,m).

enemy(nano,america).

american(west). 


### Output:

![372436409-87bda6b3-19cb-444c-b343-4a0ce5fb633544](https://github.com/user-attachments/assets/0c339678-5ced-415c-841a-f1a8a7bc207c)

### Result:
Thus the prolog programs were executed successfully and the answer of query was found.
