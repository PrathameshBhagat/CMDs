# BFS / Level order traversal
1. Take a Queue data structure. (can be linked-list/array etc. implemented as a Queue)
2. Add first vertex, to queue.
3. Pop a vertex from queue then visit it.
4. Then add all of its neighbours to queue (next nodes/vertexes).
5. Repeat step 3 & 4, stop if Queue is empty (and 3. cant pop now.).
# DFS
<details> <summary> Code to generate all possible combinations of a sting of a given length by DFS </summary>

  ```java
// l is the list with all combination generated as :- List<String> l = new ArrayList<String>();
// Executed as :- dfs( new StringBuffer(), <<Given String>>, 0);
    void dfs(StringBuffer sb, String s, int index){

         // Exit or end condition 
        if( sb.length() == length ){
    
            String newString = sb.toString();

            if( !l.contains( newString ) )
                
                l.add(  newString  );

        }

        // Exit/End condition
        if( index > s.length() - 1 )

            return;
        // Take the decision
        sb.append( s.charAt(index) );

        // Make a recursive call
        dfs( sb, s, index + 1 );

        // Back track to previous state
        sb.deleteCharAt( sb.length() - 1 );

        // Recursive call to next index with taking previous operation
        dfs( sb, s, index + 1 );

    }
  }
```
