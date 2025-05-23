# Arrays 
#### `a = b.clone() ` => only way to copy array without for loop
<details> <summary>  Sort a normal array using a comparator (1-D array) </summary>
  
  ```java

  // For normal array of string i.e.String[] - >
  Arrays.sort(n, new Comparator<String>() {
              @Override
              public int compare(String o1, String o2) {
                  // Most built objects have compareTo method you can use them
                  return o1.compareTo(o2);
              }
          });

```
</details>  

**`Arrays.sort(arr, (a, b) -> Integer.compare(a[col],b[col]));`** => Sorts a **2-D** array
<details> <summary> Sort a 2-D array using a comparator </summary>

  ```java
  Arrays.sort(array, new java.util.Comparator<int[]>() {
    public int compare(int[] a, int[] b) {
        return Integer.compare(a[0], b[0]);
    }
});
```
</details>  

**`Arrays.deepToString(int[][][]..);`** => Returns all the nested arrays in the form of a string(deepToString method)  
**`Arrays.toString(int[])`** => Returns a **1-D** array in the form of a string  
**`Arrays.stream(myArray).flatMapToInt(Arrays::stream).forEach(num -> System.out.print(num + " "));`**  
=> Flatterns a **2-D** array and prints content

# Stack !!!
**`Stack<Integer> s = new Stack();`** => Only way to create stack !!!!

# Lists 
**`Q.isEmpty()`** => Checks if a list only contains null's or has length = 0.  
**`Collections.sort(Q)`** => Sorts a list (arraylist, linkedlist, any colletion)  
**`int [] ints = list.stream().mapToInt(Integer::intValue).toArray();`** => convert list of integer  to int[].
# Map
<Details><Summary>Sort a map by key/Value by converting to list of Map entries </Summary>

  ```java
//(Modify classes as required)
Map<int[], Double> map = new  HashMap<>();

for(int[] a : points)
            
    map.put(new int[]{a[0], a[1]}, dist(a) );
// Map created, can be an normal map in place  
// Now create list and sort by comparator  
List<Map.Entry<int[], Double>> list = new ArrayList<>(map.entrySet());

list.sort(Map.Entry.comparingByValue());

```  
</Details>
<Details><Summary>Sort a map by key THEN by Value by converting to list of Map entries </Summary>

  ```java
//(Modify classes as required)
Map<Integer,Integer> map = new  HashMap<>();

for(int a : points)
            
    map.put( << first number>>, << second number>> );

// Map created, can be an normal map in place  
// Now create list and sort by comparator  
  List<Map.Entry<Integer,Integer>> l = new ArrayList<>(m.entrySet());

Collections.sort(l, (a,b) ->{

    if(a.getKey() ! = b.getKey() )

      return a.getKey().compareTo(b.getKey()) ;

    
      return a.getValue().compareTo(b.getValue()) ;
   });

```  
</Details>


# Collection

**`Collections.sort(productsList);`** => sorts any list might sort other collections if **compare method** is present
<Details><Summary>If compare method not present + shortcut </Summary>

  ```java
//(Modify arrow function as required, here the collection is a list of int[] so a&b are int[] and henceforth)
Collections.sort(L , (a,b) -> { 

            if(a[0]!=b[0]) 
                
                return Integer.compare(a[0],b[0]);

            return Integer.compare(a[1],b[1]);

        });

```  
</Details>

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
<br><br><br><br><br><br>

# Formatting required 
**`Arrays.sort(array,(optional)Comparator)`** => sort array in ascending order  

**`Arrays.stream(candidates).boxed().sorted(Collections.reverseOrder()).mapToInt(Integer::intValue).toArray();`**  
=> Sort primitive array in reverse order   
   
**`Integer.toBinaryString(i);`** => Integer to binary String conversion   
**`Integer.parseInt(binaryMaxString,2);`** => String base 2 to Integer Conversion (Binary String to Integer conversion)    

**`map.entrySet()  
  .stream()  
  .sorted(Map.Entry.comparingByValue())  
  .forEach(System.out::println);`**  
// Sorting a Map by Value and by Key ^  
// In place of fore each you may need :  
**`.collect(Collectors.toMap(Map.Entry::getKey, Map.Entry::getValue, (e1, e2) -> e1, LinkedHashMap::new));`**  
  
// For reverse order   
**`Map<K,V> newMap = map.entrySet()  
      .stream()  
      .sorted(Map.Entry.<K, V>comparingByValue().reversed())  
      .collect(Collectors.toMap(Map.Entry::getKey, Map.Entry::getValue, (e1, e2) -> e1, LinkedHashMap::new));`**   
        
      OR  
**`Map<Integer,Integer>  sorted = map.entrySet().stream()
       .sorted(Map.Entry.comparingByValue(Comparator.reverseOrder()))
       .collect(Collectors.toMap(Map.Entry::getKey, Map.Entry::getValue, (e1, e2) -> e1, LinkedHashMap::new));`**  
  
//Java String List sorting   
//By Length ->  
        **`Collections.sort( validSubStrings , Comparator.comparing(s->s.length()));`**  
//By alphabetic order ->  
        **`Collections.sort( validSubStrings );`**  
//By length then alphabetic ->  
  
**`Collections.sort( validSubStrings , (string1, string2) ->  
                if(string1.length() != string2.length())  
                    return Integer.compare(string1.length(), string2.length());  
                else return string1.compareTo( string2 ););`**  
    
