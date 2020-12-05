# Knuth-Bendix Completion (Noetherian Rewrite Rules) (Blog Post 8) 

This blog post is a continuation of my post on complexity with regards to *Abstract Reduction Systems*. There I also defined and redefined some terms that will be 
very helpful to understand before reading further. My goal in this blog post is to continue my analysis of the paper "An Introduction to Knuth-Bendix Completion" by 
A.J.J. Dick. In doing so I hope to learn more terms and mathematical strategies for assessing algorithms and also to try connections between this work and what we 
have been learning in our course. 

Here is a link to the article: 
https://www.researchgate.net/publication/220460160_An_Introduction_to_Knuth-Bendix_Completion

We have covered normal forms extensively in previous blog posts so I will keep this brief. If two different terms can be rewritten using a set of rewriting terms 
to a term that can no longer be rewritten, we say that the terms are equivalent and that the final term they can be rewritten to is a *normal form* Dick uses the 
proof of --a = a in his paper to exemplify a rewrite proof but to show my own understanding, we will attempt to prove that A + 1 = 1 for boolean algebra using the following rewriting rules: 
```
[1] (A + B)+ C = A + (B + C)
[2] A + A = A
[3] A + A' = 1
```

Consider the term A + A' + 1. 
```
A + A' + 1 
-> (A + A') + 1 [By 1]
-> 1 + 1 [By 3]
->1 [By 2]
```
Now consider the same term but parsed slightly differently.
```
A + A' + 1 
-> A + (A' + 1) [By 1]
-> A + 1 [By 3]
```

This process of determining that two terms are equivalent by starting with the same term and reducing to two different equivalent terms is called a *Non-rewrite 
proof*. I almost prefer to call it an *inverse rewrite proof* because instead of showing that two terms are equivalent in that they reduce to the same normal 
form, it shows that two terms are equivalent by reducing from some term. Dick calls this term that we reduce from the *critical term*.

Generation of these critical terms are critical (pun intended) to the functioning of our Knuth-Bendix completion. 

This is where my understanding of the paper falters slightly: 

*Unification* is the attempt to find two different terms that we know will evaluate to different reduced forms, which seems to be the whole point of these *Non-
rewrite proofs*. We begin the process of generating a *critical term* by finding a *critical pair* two different terms from which we can derive a common 
*critical term* by applying the inverse of any of our rewriting rules. 

*Superposition* is a strategy for finding critical pairs by attempting the *unification* of the left hand side of two different terms to subterms of the rule we are looking to prove. 

For instance, given our previous set of rules, A + A + 1 = A + 1 = A + (A + 1) 
*Keep in mind that A + 1 = 1* 
```
A + A + 1
-> A + 1 [By 2] 
```
And also
```
A + A + 1
-> A + (A + 1) [By 1] 
```
From this *critical pair*, we can find the *critical term* by Applying the inverse of Rule 2 and 1. 
```
A + 1 
-> A + A + 1 [By 2]
```
```
A + (A + 1)
-> A + A + 1 [By 1] 
```





