# DSA

It is a function which gives us relationship about the time as it grows when the input increases

`O(1)  <  O(log(N))  <  O(N)  <  O(N*log(N))  <  O(N^2)  <  O(N^3)  <  O(2^N)`

### What do we consider when thinking about complexity

- Always look for worst case complexity because an application with 10 users wont effect your infra but with 10000000 users lol ho jayega.
- Always look at complexity for large infinite data eg➖ `O(N^3 + log(n))` here we can ignore `log(N)` because for very large value of `N` , `log(N)` will be very small as compared to `N^3`
    
    Thus always remove the less dominant terms 
    
- Here you can see the actual time taken will be different in different systems, but we are only interested in the relationship of how the time is growing vs the size i.e in this case it is growing linearly. That is why we ignore constants.
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f61e4bbc-7564-4f27-a622-4251dffdf7d2/Untitled.png)
    

### Notations

1. `Big-Oh Notation`(Represents upper-bound)
    
    Every Big-Oh will follow this math equation, at it shows the maximum time possible
    
    You can also say like `f(N) < C1*g(N)`
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5ecd9412-b539-4f27-a925-a56debb19228/Untitled.png)
    
2. `Big-Omega`(Represents lower-bound)
    
    It is literally opposite of bigO, that is it showing the least time which will be taken by the code
    
    You can also say like `f(N) > C1*g(N)`
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ea6e13b7-15be-4027-89eb-78600f7e198b/Untitled.png)
    
3. `Theta`(Combining both)
    
    You can also say like `f(N) < C1*g(N) and f(N) > C2*g(N)`
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/4feaa73f-7af7-4e68-9bff-a84d7042d26c/Untitled.png)
    
4. `Little-Oh`
    
    This basically represents the upper bound only but unlike `BigO` , strictly less time can only be possible i.e not equal to the time-complexity we know.
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/bfda3d4f-6e5e-4155-abea-0aa08fe13de4/Untitled.png)
    
5. `Little-Omega`
    
    This basically represents the lower bound only but unlike `Big-Omega` , strictly more time can only be possible i.e not equal to the time-complexity we know.
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/31c1bf21-9cf7-4f83-b681-865ba3c05ad6/Untitled.png)
    

### Space Complexity or Auxillary Space

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/49f92307-bf56-44a8-ab84-206041f0bfb5/Untitled.png)

| Algorithms | Best Case | Worst Case | Average Case |
| --- | --- | --- | --- |
| Insertion Sort |  |  |  |
| Bubble Sort |  |  |  |
| Selection Sort |  |  |  |
| Quick Sort |  |  |  |
| Merge Sort |  |  |  |
| Counting Sort |  |  |  |
| Binary Search |  |  |  |
| Linear Search |  |  |  |

## Algorithms

## **1. Merge Sort**

It divides the given array in half, sorts each of those halves & then merges them back together. The same sorting algorithm is applied on each of these halves. The megre method copies elements from target array to helper array. We keep track where it starts and where it ends. Then, iterating over the helper array and copying smaller elements to the target array until we have traversed the whole helper array.

**Time Complexity** : O(n log n)

**Space** **Complexity** : O(n)

## **2. Bubble Sort**

In this, we start from the begnining of the array, swap the first two elements, if the first one is bigger than the second one. This process is continuously repeted until we reach the end of the array. In this way, the array elements are put in a sorted order as smaller elements bubble upto the beginning of the array.

**Time Complexity** : O(n²)

**Space Complexity** : O(1)

## **3. Insertion Sort**

In this, the array is sorted into two, the first one being sorted part at the left side & other one being unsorted part at the right side. We iterate over the array and for every iteration we pick the first element from unsorted array and insert it at the correct position in the sorted part. This process is continuously repeated until the whole array is sorted.

```c
// Insertion sort
int main(){

    int a[] = {7,8,3,2,1,4,5};
    int temp = 0;
    for (int i = 1; i < 7; i++){ // 7 8 3 2 1 4 5
        int key = a[i];
        for (int j = i; j >= 0; j--){
            if(key < a[j-1]){
                temp = a[j];
                a[j] = a[j-1];
                a[j-1] = temp;
            }
        }
    }

    for(int i = 0;i<7;i++){
        printf("%d", a[i]);
    }
}
// Here we are getting constant polynomial expression that is why we are using theta
// (because we are getting c1 and c2 --> tightly bound condition)
```

**Time Complexity** : `O(n²) in worst case` & `O(n) in Best case`

**Space Complexity** : O(1) —> This is auxillary space because the actual space complexity will be O(N)

## **4. Selection Sort**

It is the most simplest algorithm, but it is inefficient. In this we linearly sacen the whole array, find the smallest element & swap it with the first element. Then again linear scan of array, find second smallest and swap it with second element. This process is continuously repeated until the whole array is sorted.

**Time Complexity** : O(n²)

**Space Complexity** : O(1)

## **5. Quick Sort**

In this, we pick a random element & partition the array, such that all numbers that are less than the partitioning element come before it & all elements greater than it comeafter the partioning element. Repeatedly partitioning the array will eventually result into the sorted array. The time complexity depends on the position of the partitioned element which makes the sorting slower.

**Time Complexity** : O(n log( n)) in best or average & (n²) in worst case

**Space Complexity** : ****O(log(n))

## **6. Heap Sort**

Heapsort combines the better attributes of the two sorting algorithms — Merge sort & Insertion Sort. Like merge sort, it’s running time is O(n logn) & like Insertion sort, it sorts in-place. It uses **data structure, called “heap,”** to manage information.

The heapsort first builds a max-heap on the input array. In max heap, the maximum element is always stored at the root. Since the maximum element of the array is stored at the root, it can be put into its correct final position in the sorted array & exchanging it with last element of the heap. Then, heapify the heap excluding the last element. Also, the size of heap is decreased at the last element has got its correct position in the sorted array. This process is repeated, till the size of the heap becomes zero, finally resulting in a sorted array.

**Time Complexity** : O(n log( n))

**Space Complexity** : ****O(1)

## **6. Cyclic Sort**
