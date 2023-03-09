- The Framework 

  - Look for the form of the problem !
  
  -  FORM 1

  		- Go Object by Object and decide what to do with the current object.
  			- mostly used for subset , subsequences.
  			- good for building the solution incrementally.

  - Decide states and meaning

  	-  dp(level , constraint1, constraint2 , ...)

  		- Example : In a workshop there are N problems , ith problem requires {Ti,Si}
  		  You have X time and k Slots . Find the maximum skill you can get.

  		  constraints : summation(Ti) <= X
  		  				count <= K

  		  modelling the states as :

  		  		dp(level,time_taken,item_taken) -  Max skill we can get in [level .... n-1] with already 									time_taken and item_taken with limit being X and K 									       correspondingly

  	- Decide the transition 
  						  	 - -  - 		
  		(T1 )	(T2)  (T3)	| (Ti) |
  		(S1 )   (S2)  (S3)  | (Si) |  <- take ith or not take
  							 - -  -
  		when can we not take -> whenver we want as it doesnot impact the constraints

  		  		dp(level,time_taken,item_taken) = dp(level+1,time_taken,item_taken)

  		when can we take -> when the choice is feasible 
  				
  				dp(level,time_taken,item_taken) = Slevel + dp(level+1,time_taken+T_level,item_taken+1);


  	- Decide the  answer

  			our ans for level = level is max(__,__)

  	- Deciding Time Complexity

  			TC = [No Of States * (1+ AVG Transition Cost per state)]

  			for the above problem , 

  			- Calculation of #states :
  				level can take  values [0...N]
  				time_taken can take Values [0...X]
  				item_taken can take values [0....K]

  			#states = product(#states)
  					= (N * X * K)

  		   #transitions  = 2 i.e take or not take


  		   TC = N*X*K(1+2)
  		      = 3 (N * K * X) = O(NXK)

  	- Deciding Space Complexity - (#States) 

  	- Can Code Now 


- Dealing with Queries
	
	
	_ _ _ _ _ _ _ _	 ______

	[		T      ]
	instead of keeping taken till now , we can keep what is left in the state

	TC ; everytime we flush the dp array , memset takes O(#states) + O(DP)

		and assume the rec calls as O(1) <- ammortisation


- Printing solutions 
	
	- Trace the transitions that lead to the final value
													 |
													/ \
											Recheck     Backptr




- Printing All solutions
	- just backtrack 	



