There are some facts :
  
  1*- gcd(A,B) = gcd(A-B,B)
  2*- A%B = A-(A//B)*B
  3*- gcd(A,B) = gcd(A%B,B)
  4*- equation A*x+B*y=C has answer only when C mod gcd(A,B) = 0 . (A and B are integers)
  
Proof of correctness of algorithm : 

  1- A*x0 + B*y0 = gcd(A,B) (( There is no need for A to be bigger than B. I will prove it in the future)) 
  2- B*x1 + (A%B)*y1 = gcd(B,A%B) = gcd(A,B)
  3- from 2* , we can write equation 2 as : B*(x1) + (A-(A//B)*B)*y1 = gcd(A,B)
  4- after some simple works , we get : A*y1 + B*(x1-(A//B)*y1) = gcd(A,B)
  5- after comparing equation 4* with equation 4 , we get that x0 = y1 and y0 = x1-(A//B)*B .
  6- Since we can observe a recursive manner in x0 = y1 and y0 = x1-(A//B)*B , we can conclude that if we calculate x1 and y1 , then we can calculate x0 and y0 which are answers
    of our equation.With the same approach , if we calculate x2 and y2 , then we will be able to calculate x1 and y1 and after that we can calculate x0 and y0.
  7- It is obviously telling us that recursion works here properly. 
  8- The base case of our recursive method is the time when we have gcd(A,0) (( this A is NOT as same as A in equation 4* . This A has been calculated in recursion )) .
  9- In the base case , the equation would be A*xn + 0*yn = gcd(A,0)=gcd(A,B) (( two A's differ !! )). In this case xn must be 1 and yn can be any arbitrary integer. For each
    yn , we will get unique x0 and y0 .For example our x0 and y0 can be 1 and 4 when our yn is 0 and they can be 8 and -2 when our yn is 4 .
  
Now the proof for that A can be smaller than B :

  1- we have gcd(A,B) = gcd(B,A%B) .
  2- if A < B , then A%B = A .
  3- So in the first step, the algorithm will atomatically change A and B and will assign the max(A,B) to A.
