# Lambda Calculus (Blog Post 5) 
A lot of the following blog post is based off the video "Lambda Calculus" from the YouTube channel "Computerphile" They also have an excellent video
on Haskell and functional programming languages that you can find here: 
https://www.youtube.com/watch?v=LnX3B9oaKzw

Thus far we've covered Haskell as a functional programming language as well as BNFC, a converter that generates haskell code from the BNF. So what is 
happening when we actually "compile" a haskell program? 

Well, it is being transformed into a slightly altered from of Lambda Calculus. 

**Formal Definition**
Lambda Calculus is a model of computation that primarily revolves around substitution. Think of the bubble sort algorithm which we discussed in a previous
blog post. 

The Bubble Sort algorithm truly has one input, the list which we wish to sort. Some iterations of the algorithm may also pass in the length of the list 
for ease of implementation but that is not important to our mathematical understanding of what is going on. 

Imagine for a moment that you had no idea how the Bubble Sort algorithm worked. Only that a list of integers was passed in and when it was passed out it
was listed in the correct order from least to greatest. This idea, of knowing the output and input of a function but not knowing or caring exactly how
it is done is sometimes colloquially called **"Black Boxing"**. [^1] 

The lambda calculus has three essential parts: variables, defintions of functions, and applications of functions. It would be written simplistically as: 
```
λ(function variable). (function implementation) 
```
What is fascinating about this is that using the lambda calculus, we can encode really any kind of function that we would want to. In the case of Bubble 
Sort, it would look something like this: 
```
λ(list of integers). (for all indexes, compare every other index and switch if the value of the first is greater than the value of the second) 
```
This might be a little confusing so let's do another example this time with a function whose algebra we can easily write out. How about the equation 
```
f(x) = x²+2
```

[^1] This occurs a lot in computer architecture textbooks that need to cover specific aspects of 
how a component functions without exasperating the reader with the CMOS implementation or each exact logic gate. 

