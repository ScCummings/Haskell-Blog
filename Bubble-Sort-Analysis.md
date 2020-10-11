# Bubble Sort Analysis (Blog Post 2)
Continuing on from our previous discussion regarding recursion and functional programming, let's take a look at one of the most intuative, albiet slow 
sorting algorithms, the bubble sort. 

Given an array of integers in C++: 
```
int numbers[5] = {4, 1, 0, 3, 2};
```
How might we sort the values in an iterative manner? 
Bubble sort merely indexes through each value, compares it to every other value in the array, and then switches if the value is less than the current value.
In code: 
```
void bubbleSort(int numbers[], int size)  
{  
    int i, j;  //iterator values
    for (i = 0; i < size-1; i++){ //for every value in the array   
      for (j = 0; j < n-i-1; j++){ //compare every value in the array
        if (arr[j] > arr[j+1])  
            swap(&arr[j], &arr[j+1]);  [^1]
       }
     }
 }
 ```
 This algorithm will certainly work but will slow down considerably as the size of our list increases.
 
 Now consider how you might write this function in Haskell. One issue is that bubble sort is not necessarily defined recursively, and so the logic is less
 intuative. Lets start by defining what we expect to pass in as parameters and what we expect to be returned:
 ```
 bubbleSort' :: (Ord a) => [a] -> [a] //This much is also given in our lecture notes
 ```
 But now let's consider how we would write out the rest of the algorithm: 
 ```
bubbleSort' xs i //This is simply defining a function "bubbleSort" with parameters s (x indicates a list) and i, an interator value similar to what we saw 
                 //in the previous C code. 
    | i == (length xs) = xs
    | otherwise = bubbleSort' (bubbleSort'iter xs) (i + 1) //recursively iterate through the list, calling bubbleSort' on each index. 
bubbleSort :: (Ord a) => [a] -> [a] //create another bubblesort function
bubbleSort xs = bubbleSort' xs 0 //run a recursive version of the bubble sort through the entire list, starting at the beginning.
  ```
  The previous code is not my own and can be found at the link:  https://smthngsmwhr.wordpress.com/2012/11/09/sorting-algorithms-in-haskell/#bubble_sort
  
  However, I'd like to go through it and point out something pretty incredible about it's implementation. 
  It takes an algorithm that is normally iterative and makes it recursive. Something interesting about Haskell is not just that writing in a purely 
  functional language allows for easier to read recursive programs, but that by writing in what is essentially mathematical expressions, the user
  can take basic algorithms and work them into recursive programs by using the nature of haskell. 
  
  As the above website puts it: 
  "What distinguishes Haskell is that it is a purely functional language, without state and variables. 
  As a result statements in it are very close to mathematical expressions."

