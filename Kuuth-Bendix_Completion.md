#Knuth-Bendix Completion (Blog 7)

Based on the 1991 paper "An Introduction to Knuth-Bendix Completion" by A.J. Dick, this blog post will attempt to break down the major components of the paper as 
well as draw ties between them and what we have learned so far both with regards to programming and computer science theory but also what we have learned about 
the programming language Haskell. 

The article can be found here: https://www.researchgate.net/publication/220460160_An_Introduction_to_Knuth-Bendix_Completion

The process of Knuth-Bendix Completion is designed to help transform a typcial set of rules or relations that we might see form the basis of an ARS into a different 
rewriting system that could be described as confluent. 

We have covered both *ARS (Abstract Reduction Systems)* as well as *Confluence* in previous blog posts but for the sake of the reader as well as for my sake, let's 
**very briefly** cover them once again. 

+ An *Abstract Reduction System* is formally defined as a set A together with a relation. In other words, it is a set of terms as well as a set of rules or 
relations for rewriting those terms. 

+ An *ARS* is said to be confluent if whenever an element reduces to either an element y or an element k, then y and k are joinable. 

+ y and k are said to be *joinable* if both y and k reduce to the same element. 

Given that the reader understands the previously listed terms as well as some basic understanding of logic, we can skip the first three sections. Trust me, you 
aren't missing much. The author defines a few terms and gives two indepth examples of algebraic proofs. 

The fourth section is probably of more interest to us as it introduces a new and 
important way of looking at algorithms. Dick defines ">" as a symbol contrasting the
"Complexity" of specific terms. 

Consider the hypothetical set of rules: 
```
aa -> b
ab -> a
ba -> a
bb -> b
```
Then using the symbol for complexity ">", we can see that. 
```
aababababb > a
babb > a
aaaabbbb > b
```
For the above example, it was fairly easy to find the normal form of terms on the 
right using our ARS. However, as our ARS becomes more complex and adds more and more 
operations, we may find it helpful to assess an algorithm's "Complexity" via trees. 

Take the 
