## Two Pointers Pattern
Solve the problems using two cursors by traversing through different direction in array.

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
