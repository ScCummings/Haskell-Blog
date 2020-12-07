# Programming Languages and Semiotics 2 (Blog Post 17)

This is a continuation of my blog post 16 which covered the introduction of this paper: 

https://dl.acm.org/doi/pdf/10.1145/365230.365249?casa_token=vQoIiN5Vx4gAAAAA:imblU2qrUlhqlnGYbCrFFf38NwfS5DzGo-rBMXz_ZvlHDYVHf0WiL6Sj8TrpvjBQbYWWXKCNUtMV3xY

The paper is concerned with drawing historical and practical connections between the fields of computer science and semiotics. Given we are in a programming 
languages course and assessing the relationship between logic and language is part of the goal of that course, I hope covering this paper in my blog will be 
helpful in my overall understanding of the subject and its applications in the field of software engineering. 

In the last blog post, we covered Chales Morris, a philosopher and founder of the field of semiotics. He was notably not a computer science and was moreso 
interested in the human aspects of language and semiotics. 

An interesting question is posited by the paper: Why don't we just code in natural language? It certainly would make introductory computer science courses much 
easier to understand. While much syntax can be learned rather quickly, there is still a big difference between: 

```
Find every instance of the word "language" in the book. 
```

and 

```
for(String word:Book){
  if (word.equals("language"){
    listOfInstances.add(Book[i]);
   }
   i++;
}
```

Yet the paper lays out four very important concepts that we lose when describing algorithms in natural language: 

+ Natural Language can be ambigious and therefore operations can be ambiguous. For instance, consider writing a parser for the English. The idea spins the head. 
For the above sentence, we don't even know where we are looking for the word "language" until the very end of the sentence, even though it logically makes sense 
to explain where we are looking first. 

+ Assumptions are excluded. Granted, in my opinion this argument is rather non-unique as I make incorrect assumptions about how code works all the time. Though 
it does make sense that error messages written for a piece of natural language would be impossible to debug. Consider the following instruction: 
```
I do not to run or lift weights.
```
This is ambiguous and assumes that the "not" term extends to all arguments after it within the same sentence. To write it in code would look like: 
```
!run ||liftWeights
```
as opposed to the correct assumption of 
```
!(run || liftWeight) 
```

+ Notation is more clear. This argument is fairly similiar to the other two so I won't provide a new example for it. 

+ Expressions become shorter. This is one is probably true on balance though not true in every instance. Take for example: 
```
int x += 5; 
```
which would need to be written in natural language as: 
```
The integer x is incremented by 5 and then is asserted as that value.
```
which is quite the mouthful. 

I am still very much enjoying this paper and will likely write my final blog post on it as well. 

