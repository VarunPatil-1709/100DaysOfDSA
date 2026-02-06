# Day 2 – Arrays

## Problem 1: Rotate Array by One (Simple 2 Pointers)

```java
class Solution {
    public void rotate(int[] arr) {
        // code here
        int first = arr[arr.length-1];
        for(int i = arr.length-1;i>0;i--){
            arr[i]=arr[i-1];
        }
        arr[0]=first;
    }
}
```

## Problem 2: Maximum sum of a subarray

```java
class Solution {
    int maxSubarraySum(int[] arr) {
        // Code here
        int max =Integer.MIN_VALUE;
        int count = 0;
        for(int i=0;i<arr.length;i++){
            count+=arr[i];
            if(count<0){
                max=Math.max(count,max);
                count=0;
            }
            else{
                max=Math.max(count,max);
            }
        }
        return max;
    }
}
```

## Problem 3: Union of Arrays with Duplicates (HashSet)

```java
class Solution {
    public int findDuplicate(int[] nums) {
        int [] arr = new int[nums.length];
        for(int i = 0;i<nums.length;i++){
            int temp = nums[i];
            if(arr[temp]==1){
                return temp;
            }
            else{
                arr[temp]=1;
            }

        }
        return -1;

    }
}
```
