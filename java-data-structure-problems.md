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
   
### 2) Find missing number between 1 - 100

```
import java.util.BitSet;

class HelloWorld {
    public static void main(String[] args) {
        int numbers[] = {1,2,3,5};
        int missingCount = 1;
        
        BitSet bitSet = new BitSet(5);
        
        for(int number : numbers) {
            bitSet.set(number -1);
        }
        
        int lastMissingIndex = 0;
        for(int i=0; i < missingCount; i++){
            lastMissingIndex = bitSet.nextClearBit(lastMissingIndex);
            System.out.print(++lastMissingIndex);
        }
    }
}
```
