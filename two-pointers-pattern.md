## Two Pointers Pattern
To solve the problems using two cursors by traversing through array in different direction.

### 1) Palindrome<br>
Find palindrome of given string?<br>
Ex<br>
input: malayalam<br>
output: Given string is palindrome<br>

<b>Time Complexity: O(n)</b>

```
class HelloWorld {
  public static void main(String[] args) {
      
      String name = "malayalam";
      
      int length = name.length() - 1;
      long half = Math.round(Double.parseDouble(name.length()+".0")/2);
      
      for(int i=0;i<half;i++){
          // Break if both pointers are same
          if(i == (length - i)){
            break;
          }
          
          if(name.charAt(i) != name.charAt(length - i)){
              System.out.println("Given string is not palindrome");
              return;
          }
      }
      System.out.println("Given string is palindrome");
  }
}
```

### 2) String Reverse<br>
Ex<br>
input: krishna<br>
output: anhsirk<br>

<b>Time Complexity: O(n)</b>

```
class HelloWorld {
    public static void main(String[] args) {
        String name = "krishna";
        int endIndex = name.length() - 1;
        long maxItr = Math.round(Double.parseDouble(name.length()+".0") / 2);
        String prefix = "";
        String suffix = "";
        for(int startIndex=0;startIndex < maxItr;startIndex++,endIndex--){
            if(startIndex < (name.length() - maxItr))
                suffix = name.charAt(startIndex) + suffix;
            
            prefix += name.charAt(endIndex);
            count++;
        }
        System.out.println(prefix + suffix);
    }
}
```

### 3)Rotate Array<br>
   i.e <br>
   1)Rotate entire array<br>
   input: arr=[1,2,3,4,5,6,7]<br>
   output: arr=[7,6,5,4,3,2,1]<br>
   ```
      class HelloWorld {
          public static void main(String[] args) {
              //Rotate Array
              int arr[] = {1,2,3,4,5,6,7};
              int cursorA = 0;
              int cursorB = arr.length-1;
              while(cursorA < cursorB){
                  int last = arr[cursorA];
                  int first = arr[cursorB];
                  arr[cursorA] = first;
                  arr[cursorB] = last;
                  cursorA++;
                  cursorB--;
              }
              for(int i=0; i < arr.length;i++){
                  System.out.print(arr[i]+",");
              }
          }
      }
   ```
