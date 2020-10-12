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
it is done is sometimes colloquially called **"Black Boxing"**.[^1] 

[^1] This occurs a lot in computer architecture textbooks that need to cover specific aspects of 
how a component functions without exasperating the reader with the CMOS implementation or each exact logic gate. 

