# Day 4 – Arrays

## Problem 1: Merge Intervals

```java
class Solution {
    public int[][] merge(int[][] intervals) {
        Arrays.sort(intervals, (a, b) -> Integer.compare(a[0],b[0]));
        List<int[]> final1 = new ArrayList<>();


        int [] prev = intervals[0];
        for(int i = 1; i<intervals.length;i++){
            if(prev[1]>=intervals[i][0]){
                if(intervals[i][1]>prev[1]){
                    prev[1]=intervals[i][1];}
            }
            else{
                final1.add(prev);
                prev=intervals[i];
            }
        }
        final1.add(prev);
        return final1.toArray(new int [final1.size()][]);
    }
}
```

## Problem 2: Best Time to Buy and Sell Stock

```java
class Solution {

    public int maxProfit(int[] prices) {
        int profit = 0;
        int buy = prices[0];
        for(int i = 1; i<prices.length;i++){
            int count = prices[i]-buy;
            profit = Math.max(profit, count);
            if(buy>prices[i]){
                buy = prices[i];
            }

        }
        return profit;

    }
}
```

## Problem 3: Next Permutation

```java
class Solution {
    public void nextPermutation(int[] nums) {
        int n = nums.length;
        int i = n-2;

        while(i>=0 && nums[i]>=nums[i+1]){
            i--;
        }
       if(i>=0){
        int j = n-1;
        while(nums[j]<=nums[i]){
            j--;
        }
        swap(nums,i,j);
       }
       reverse(nums,i+1);
    }
    public void swap(int [] arr, int a, int b){
        int temp = arr[a];
        arr[a]=arr[b];
        arr[b]=temp;
    }
    public void reverse(int [] arr, int a){
        int n = arr.length-1;
        while(a<n){
            swap(arr,a,n);
            a++;
            n--;
        }
    }
}
```
