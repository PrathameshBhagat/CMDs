
<details> <summary> Bit Manipulation </summary>

## Check a bit 
 **```result = num & (1 << position)```**  
(position-1) may be required
## Set a bit ( '1' ?)

 **```num = num | (1 << position)```**

  Example:  
    1100  = 1000  | (1 << 2)  (Binary representation)  
     (12) => 1100    
     (8) => 1000  
     (4) =>  1<<2 => 100  

## Unset a bit (Set a '0' ? )
 **```num = num & ~(1 << position)```**
    
   Example:   
1000 = 1100 & ~(1 << 2)  (Binary representation)  
(8)    (12)     (4)

## Flip a bit
 **```num = num ^ (1 << position)```**
    
   Example:  
1000 = 1100 ^ (1 << 2)  (Binary representation)  
(8)    (12)     (4)
</details>

##  Breadth first search / Level order traversal
1. Take a Queue data structure. (can be linked-list/array etc. implemented as a Queue)
2. Add first vertex, to queue.
3. Pop a vertex from queue then visit it.
4. Then add all of its neighbours to queue (next nodes/vertexes).
5. Repeat step 3 & 4, stop if Queue is empty (and 3. cant pop now.).
## Depth first search (DFS)
<details> <summary> Code to generate all possible combinations of a sting of a given length by DFS </summary>

  ```java
// l is the list with all combination generated as :- List<String> l = new ArrayList<String>();
// Executed as :- dfs( new StringBuffer(), <<Given String>>, 0);
    void dfs(StringBuffer sb, String s, int index){

        // Base case or Exit/End condition
        if( sb.length() == length ){
    
            String newString = sb.toString();

            if( !l.contains( newString ) )
                
                l.add(  newString  );

        }

        // Base case or Exit/End condition
        if( index > s.length() - 1 )

            return;

        // Take the decision, (can be taken combinedly in below dfs call itself as well)
        sb.append( s.charAt(index) );

        // Make a recursive call
        // In (first) call for any recursion of dfs etc. you can remove + 1 from index + 1 if a decision can be taken any number of times but handle base case properly
        // remember if index is not changed in the next call (assuming frst call does not have + 1) then the call is same as this call to dfs itself so stack overflow exception wil occur  
        dfs( sb, s, index + 1 );

        // Back track to previous state
        sb.deleteCharAt( sb.length() - 1 );

        // Recursive call to next index with taking previous operation
        dfs( sb, s, index + 1 );

    }
  }
```

 </details>

 
> ### Longest Inreasing subsequence (LIS)
> via striver can explain all this including memoiation  & tabulation

### DFS or Recursion
Steps :- 
1) Call dfs()
2) Base cases.
3) Take (one of) the decision. (program may end here)
4) Back track and take other possible decisions or just combine 3) & 4) by looping all posibilities.
5) return the states 
# Dynamic Progrmming
### Memoization :  -  
 1) All steps in recursion/dfs
 2) Express in terms of indexes if required (coordinate shift may be required to make  -1 -> n to 0 -> or etc.) 
 3) Note changes in index and parameters in dfs ore recursin parameters.
 4) Then in reursion add:
  
  ```java

    A)
        if( << if this index exist int dp array or object >>" )

            return dp[index] << or equivalent >>  

  
    // After this, before returning the solved solution (at the end), add >>


    B) 
          dp[index] = << computed solution >>  

        return;
     
```
   

### Tabulation :  :
1) All steps in memoization
2) Note index changes (from above) and create for loops for them (coordinate shift or increacse dp size by 1, etc.) 
3) Copy recurrence code in dfs/recursion and pasrte in loops
4) return dp[] == ... becomes dp[] = ....
5) Memori optimise if you use   n * m and use previous row/ column only to solve current state. 

