#### Java Problems

### 1) Reverse Integer<br>
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

### 2) Find missing number
   i.e<br>
   input: arr=[1,2,4,5], n=5<br>
   output: 3<br>
```
   class HelloWorld {
       public static void main(String[] args) {
           
           int arr[] = {1,2,4,5};
           int n=5;
           int sum = 0;
           for(int i=0; i < arr.length; i++){
               sum = sum + arr[i];
           }
           
           int sumOfAllNum = (n * (n + 1)) / 2;
           System.out.print("Missing number is -> "+(sumOfAllNum - sum));
       }
   }
```

### 3) Find sum of pair between any two numbers<br>
   i.e<br>
   input: arr=[1,8,4,3]<br>
   output: 7<br>
   ```
   import java.util.Map;
   import java.util.HashMap;
   
   class HelloWorld {
       public static void main(String[] args) {
           int[] nums = {1,8,4,3};
           int target = 7;
           Map<Integer, Integer> numMap = new HashMap<>();
           
           for(int i=0; i < nums.length; i++){
                   
               int remaingVal = target - nums[i];
               if(numMap.containsKey(remaingVal)) {
                   System.out.print("Array Index -> {"+numMap.get(remaingVal)+","+i+"}");
                   System.out.print("Array Value -> {"+remaingVal+","+nums[i]+"}");
                   break;
               }
               numMap.put(nums[i], i);
           }
       }
   }
```
