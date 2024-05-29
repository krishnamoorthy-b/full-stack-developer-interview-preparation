
## Sliding Window Pattern

### 1) Pair with given sum<br>
Ex<br>
input: arr[] = {1, 4, 2, 10, 23, 3, 1, 0, 20}, k = 4<br>
output: 39<br>

 <b>Time Complexity: O(maxItr)</b>

```
class HelloWorld {
    public static void main(String[] args) {
        int k = 4;
        int arr[] = {1, 4, 2, 10, 23, 3, 1, 0, 20};
        
        int maxSum = 0;
        int windowSum = 0;
        
        // Calculate the sum of the first window
        for (int i = 0; i < k; i++) {
            windowSum += arr[i];
        }
        maxSum = windowSum;
        
        // Slide the window over the array
        for (int i = k; i < arr.length; i++) {
            windowSum += arr[i] - arr[i - k];
            maxSum = Math.max(maxSum, windowSum);
        }
        
        System.out.println(maxSum);
    }
}
```
