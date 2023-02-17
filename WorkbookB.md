## Q1: Identify and explain the workings of TWO sorting algorithms and discuss and compare their performance/efficiency (i.e. Big O)

----

### Bubble sort O(n<sup>2</sup>)

Bubble sorting makes passes through an array and rearranging two elements at a time in order of significance (ascending/alphabetical order.) It will do this in ```n-1``` passes, where n is the length of the array and two entries at a time, and only sort them if they are out of order with eachother. Then, it moves up one index and does the same for index 2 & 3, and so forth until the second last index, again ```n-1``` times. 

For each data entry to this array, it will increase the sorting time by (n-1)*(n-1) times, which makes the worst case condition O(n<sup>2</sup>), due to the nested loops making it multiplicitive. It can be optimized slightly to finish when entries are sorted, but the average to worst case conditions are still considered O(n<sup>2</sup>).

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
### Bucket sort O(n+k)

Bucket sort is excellent when you have a (roughly) evenly distributed set of data to sort. In the first pass, all data entries are assigned into defined "buckets". For example, for the numbers 1-100, you may have buckets for intervals of 5, 10, 20, 25 etc depending on how many data entries you had. Then, each bucket is then individually sorted using another sorting algorithm, e.g. insertion sort, comparison sort or merge sort.

For each data entry to this array it will increase the sorting time on **average** by n+k times, where n is the number of of data entries and k is the number of buckets. The worst case scenario is all the data ends up in one bucket, then the time-complexity is limited to the sorting method of inside the bucket (which would usually fall between O(nlogn) to O(n<sup>2</sup>)). 

The use of Bucket sorting should therefore be very intentional compared to most sorting methods as it is most effective with an even distribution. 

The following is psuedocode for Bucket sorting from GeeksForGeeks.<sup>1

```
bucketSort(arr[], n)
1) Create n empty buckets (Or lists).
2) Do following for every array element arr[i].
.......a) Insert arr[i] into bucket[n*array[i]]
3) Sort individual buckets using insertion sort.
4) Concatenate all sorted buckets.
```




## Q2: Identify and explain the workings of TWO search algorithms and discuss and compare their performance/efficiency (i.e. Big O)

----

### Linear Search O(n)

Search algorithms have one limitation being that they (usually) require a sorted array for them to search through. Linear search however does not have that requirement, as it will search through every single entry to find that piece of data one at a time, hence having a linear time complexity. Every data entry is one more it has to search through (until it finds the data). 

This is a very slow method, but purely has the advantage of being able to search through unsorted data and is extremely simple to implement & understand, and does not require any extra memory. This also makes it relatively okay for small sets of data, but becomes slow for larger sets (and therefore not prefferable in arranged data).

An example of this code would look like below:

```py
array = [21, 99, 56, 13, 67, 9, 81, 1]
search = 81

def linear_search(data, search_term):
    for i in range(0, len(array)):
        if array[i] == search:
            return f"your element is present at position {i}"
    return "Your element is not present in the array."

print(linear_search(array, search))
```

----

Interpolation Search O(log log n)

Interpolation Search can be used on sorted arrays to find an element, and works particularly well in large sets of data, and, when the data is relatively uniformly distributed. 

Similar to its variation **binary search**, Interpolation search will select the middle element, then compare it to the desired value. If it is not equal, it will then check if it is smaller or larger (just like binary search). What makes the two different is Interpolation search will then compare how close the values are, and will search closer to the value instead of splitting in the middle again if the two are close in value. 

This makes it excellent for large sets of data as it will reduce the amount of splits needed each time, however it is much more complicated to program and understand than binary search, and can be slower than binary if the data set is not large, and not (relatively) uniform. 

Used appropriately, binary search is O(logn) for time complexity, but the added efficiency in Interpolation makes it O(log log n). Binary search is O(logn) as it needs one extra step every time the data is doubled (due halving the elements in every search). Interpolation takes this a step further by comparing that value to those at the upper and lower end, however this is again only accurate in well distributed data. 


## References

 (1) https://www.geeksforgeeks.org/bucket-sort-2/