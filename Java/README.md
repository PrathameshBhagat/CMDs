# Arrays 

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
<details> <summary>=> Sort a 2-D array using a comparator </summary>

  ```java
  Arrays.sort(array, new java.util.Comparator<int[]>() {
    public int compare(int[] a, int[] b) {
        return Integer.compare(a[0], b[0]);
    }
});
```
</details>  

**`Arrays.deepToString(int[][][]..);`** => Returns all the nested arrays(deepToString method)  
**`Arrays.toString(int[])`** => Returns a **1-D** array  
**`Arrays.stream(myArray).flatMapToInt(Arrays::stream).forEach(num -> System.out.print(num + " "));`**  
=> Flatterns a **2-D** array and prints content

# Lists 
**`Q.isEmpty()`** => Checks if a list only contains null's or has length = 0.  
**`Collections.sort(Q)`** => Sorts a list (arraylist, linkedlist, any colletion)  

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

# Formatting required 
**`Collections.sort(productsList);`** => sorts any list might sort other collections if comparable methord is present
  
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
**`map.entrySet()  
      .stream()  
      .sorted(Map.Entry.<K, V>comparingByValue().reversed())  
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
    
