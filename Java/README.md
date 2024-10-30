# Arrays 

`Arrays.sort(arr, (a, b) -> Integer.compare(a[col],b[col]));` => Sorts a **2-D** array
<details> <summary>=> Sort a 2-D array using a comparator </summary>

  ```java
  Arrays.sort(array, new java.util.Comparator<int[]>() {
    public int compare(int[] a, int[] b) {
        return Integer.compare(a[0], b[0]);
    }
});
```
</details>  

`Arrays.deepToString(int[][][]..);` => Returns all the nested arrays(deepToString method)  
`Arrays.toString(int[])` => Returns a **1-D** array  
`Arrays.stream(myArray).flatMapToInt(Arrays::stream).forEach(num -> System.out.print(num + " "));`  
=> Flatterns a **2-D** array and prints content

# Lists 
`Q.isEmpty()` => Checks if a list only contains null's or has length = 0.  
`Collections.sort(Q)` => Sorts a list (arraylist, linkedlist, any colletion)  
# DFS 
<details> <summary>Count nodes in a binary tree by DFS </summary>

  ```java
  int countNodes(TreeNode root) {
        if(root == null)
            return 0;
        return (1 + countNodes(root.left) + countNodes(root.right));
  }
```
</details>
