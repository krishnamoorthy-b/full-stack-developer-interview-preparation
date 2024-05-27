### Two Pointers Pattern
If use two cursors to solve any problem called two pointer patterns.

## 1) Palindrome<br>
Find palindrome of given string?
Ex<br>
input: malayalam<br>
output: malayalam is palindrome<br>

 <b>Time Complexity: O log(n)</b>

```
class HelloWorld {
  public static void main(String[] args) {
      
      String name = "malayalam";
      int lentgh = name.length() - 1; //8
      int half = Math.round(name.length()/2);
      
      for(int i=0;i<half;i++){
          //m != m
          if(name.charAt(i) != name.charAt(lentgh - i)){
              System.out.println("Given string is not palindrome");
              return;
          }
      }
      System.out.println("Given string is palindrome");
  }
}
```
