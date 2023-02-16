## Q1: Identify and explain the workings of TWO sorting algorithms and discuss and compare their performance/efficiency (i.e. Big O)

----

### Bubble sort O(n<sup>2</sup>)

Bubble sorting makes passes through an array and rearranging two elements at a time in order of significance (ascending/alphabetical order.) It will do this in ```n-1``` passes, where n is the length of the array and two entries at a time, and only sort them if they are out of order with eachother. Then, it moves up one index and does the same for index 2 & 3, and so forth until the second last index, again ```n-1``` times. 

For each data entry to this array, it will increase the sorting time by (n-1)*(n-1) times, which makes the worst case condition O(n<sup>2</sup>). It can be optimized slightly to finish when entries are sorted, but the average to worst case conditions are still considered O(n<sup>2</sup>).

A coding example would look like below, where you can see the nested loops. The worst case scenario for this sorting method, is if they are all organized in descending order. This performance is considered quite poor and does substantially increase working time with large sets of data.

```py
def bubbleSort(array):
    n = len(array)
    for a in range(n-1):
        for b in range(0, n-a-1):
            if array[b] > array[b + 1]:
                array[b], array[b + 1] = array[b + 1], array[b]
    print(array)

array = [21, 99, 56, 13, 67, 9, 81, 1]

bubbleSort(array)
```

----
Bucket sort O

https://www.geeksforgeeks.org/bucket-sort-2/
https://en.wikipedia.org/wiki/Bucket_sort
https://www.bigocheatsheet.com/





## Q2: Identify and explain the workings of TWO search algorithms and discuss and compare their performance/efficiency (i.e. Big O)

----



