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

### 4)Find first 10 fibonacci series<br>
   i.e <br>
   1)Basic approach by sum of two preceding values in list. <br>
   output: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34<br>
   ```
      import java.util.List;
      import java.util.ArrayList;
      
      class HelloWorld {
          public static void main(String[] args) {
              
              List<Integer> fibonacciNum = new ArrayList<>();
              fibonacciNum.add(0);
              fibonacciNum.add(1);
              int numCount = 8;
              int i=2;
              
              while(numCount > 0){
                  fibonacciNum.add(fibonacciNum.get(i-2) + fibonacciNum.get(i-1));
                  i++;
                  numCount--;
              }
              
              fibonacciNum.forEach( num -> System.out.print(num + ", "));
          }
      }
   ```

   2)Recursive approach by sum of two preceding values in list. <br>
   output: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34<br>
   ```
      import java.util.List;
      import java.util.ArrayList;

      class HelloWorld {
          public static void main(String[] args) {
              
              //fibonacci series with recursion
              List<Integer> nums = new ArrayList<>();
              nums.add(0);
              nums.add(1);
              int n=9;
              int i=2;
              
              findPalindrome(i,n, nums);
              nums.forEach( num -> System.out.print(num + ", "));
          }
          
          public static void findPalindrome(int i, int n, List<Integer> nums){
              if(!(i > n)) {
                  nums.add((nums.get(i-2) + nums.get(i-1)));
                  i += 1;
                  findPalindrome(i, n, nums);
              }
          }
      }
   ```
