# Day 2 – Arrays

## Problem 1: Sort 0s, 1s and 2s (Dutch National Flag Algo)

````java
class Solution {
    public void sort012(int[] arr) {
        int low =0;
        int mid =0;
        int high=arr.length-1;

        while(mid<=high){
            if(arr[mid]==0){
                swap(arr,low,mid);
                low++;
                mid++;

            }
            else if(arr[mid]==1){
                mid++;
            }
            else{
                swap(arr,mid,high);
                high--;
            }
        }

    }
    public void swap(int [] arr , int i, int j){
        int temp =arr[i];
        arr[i]=arr[j];
        arr[j]=temp;
    }
}```

## Problem 2: Move all negative numbers to the beginning (Two Pointers)

```java
````

## Problem 3: Union of Arrays with Duplicates (HashSet)

```java
class Solution {
    public static ArrayList<Integer> findUnion(int[] a, int[] b) {
        // code here
        HashSet<Integer> hs = new HashSet<>();
        for(int i =0;i<a.length;i++){
                hs.add(a[i]);
        }
        for(int i =0;i<b.length;i++){
                hs.add(b[i]);
        }
        ArrayList<Integer> fia = new ArrayList<>(hs);
        return fia;
    }
}
```
