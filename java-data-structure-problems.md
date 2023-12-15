# Java data structure problesms

### 1) Check if pair with given sum exists in array<br>
   i.e<br>
   Input: Array { 1, 4, 3, 6, 5, 8 }, sum=8<br>
   Output: 3 + 5 = 8
   
```
import java.util.*;

class HelloWorld {
    public static void main(String[] args) {
        // check if pair with given sum exists in array
        int a[] = { 1, 4, 3, 6, 5, 8 };
        int n = 8;
        
        /* 
        * Time Complexity: O(n)
        */
        HashSet<Integer> listOfItems = new HashSet<>();
        for(int i=0; i < a.length; i++) {
            int remaining = n - a[i];
            if(listOfItems.contains(remaining)) {
                System.out.println(remaining + " + " + a[i]
                + " = " + (remaining + a[i]));
            }
            listOfItems.add(a[i]);
        }
    }
}
```

### 2) Reverse Integer<br>
   Reverse integer and reverse Integer range would be 32 bit [-2^32 to 2^32 -1], If it's goes beyond that then return 0<br>
   i.e<br>
   input: 123<br>
   output: 321

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
   
