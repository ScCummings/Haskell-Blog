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
For the above example, it was fairly easy to find the normal form of terms on the right using our ARS. However, as our ARS becomes more complex and adds more and 
more operations, we may find it helpful to assess an algorithm's "Complexity" via trees. 

Take the set of rules: 
```
aa -> b
ab -> a
ba -> a
bb -> b
a + a -> a
a + b -> b
b + a -> b
b + b -> b
```
Then to assess the following statements: 
```
[1]:(aa)+(bab)+(babbab)+(bb) > b
[2]:(bab)+(abab)+(aaaaba)>b
```
It can become valuable to describe the terms and operations as parse trees: 
```
[1]:                   +
                      - -
                     -   -
                   -      - 
                  +        + 
                 - -      - - 
               -    -    -    -
             -       -  -      - 
          (aa)    (bab)(babbab)(bb)
```

An interesting topic that we haven't covered in class but which as integral to understanding further aspect of Knuth-Bendix completion are *Noetherian Rewrite 
Rules*. A set of rewrite rules as we have seen above are said to be Noetherian if they are *well-founded*,*stable*, and *monotonic.* I will conclude this blog 
post by informally defining those terms. 

**Well-founded:** Each subset of terms that can be applied to our rewriting rules has a least some term that is more complex (>) than the term's normal form. 

**Stable:** Following each execution of a rule from our rewriting rules, the term rewritten is more complex (>) than our new term

**Monotonic**: All rewriting rules are reversible. 

I will likely do a separate blog post of Netherian Rewrite Rules as I feel they are complex enough that they deserve their own. 
