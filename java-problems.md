#### Java Problems

### 1) Reverse string<br>
  ```
  class HelloWorld {
      public static void main(String[] args) {
          String name = "krishnamoorthy";
          String reverseName = "";
          for(int j=(name.length() - 1);j >= 0;j--){
              reverseName += name.charAt(j);
          }
          System.out.println(reverseName);
      }
  }
  ```

### 2) Reverse Integer<br>
   Reverse integer and reverse Integer range would be 32 bit [-2^32 to 2^32 -1], If it's goes beyond that then return 0<br>
   i.e<br>
   input: 123<br>
   output: 321<br>
   ```
   class HelloWorld {
    public static void main(String[] args) {
        int reverseNum = reverse(1234);
        System.out.println("reverseNum ->"+reverseNum);
    }
    
    public static int reverse(int x) {
        long reverseNumber = 0;
        while(x != 0){
            int remainder = x % 10;
            reverseNumber = reverseNumber * 10 + remainder;
            x = x / 10;
        }
        if (Integer.MAX_VALUE < reverseNumber || Integer.MIN_VALUE > reverseNumber)
            return 0;
        return (int) reverseNumber;
    }
  }
```
