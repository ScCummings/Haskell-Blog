# Computing Normal Forms and Outermost Reduction (Blog Post 6) 

While the process of computing normal forms is not incredibly complicated, it is integral to analysing algorithms and developing invariants for them, both of 
which are important steps that we will take over the course of this blog. The purpose of this blog post is not only to review the basics of Abstract Reduction 
Systems and Normal Forms from class but also to go deeper into their history and connection to the Backus-Naur Form which we have previously discussed. 

Before we can understand Normal Forms, we need to understand Abstract Reduction Systems and why they are useful in the context of software development. Abstract 
Reduction Systems have two distinct parts, a *set* of components or values as well as a set of rules, operations or computations otherwise known as a *relation*. 

In an binary expression, our set of components is fairly simple. To maintain the naming conventions used within the lecture notes we will define this as the set
A: 
```
{0,1}
```
Our relation is more complex though. For the sake of our example, the boolean gate "AND" could be written as a set of rules such as: 
```
0 * 0 -> 0 or 00 -> 0
0 * 1 -> 0 or 01 -> 0
1 * 0 -> 0 or 10 -> 0
1 * 1 -> 1 or 11 -> 1
```
In the field of Digital Logic we call these sets of rules a *truth table*. 

The formal definition for a normal form is some expression a that is contained within the range of our set of components A and that is none reducible by our set 
of relations. I will do three quick examples to demonstrate this. 

```
The set {011001001010} 
011001001010->01100100100->0110010010->011001000->01100100->0110010->011000->01100->0110->010->00->0
```
```
The set {111111}
111111->11111->1111->111->11->1
```
```
The set {111110}
111110->11110->1110->110->10->0
```
From these it is fairly intuative to see that the only means of getting 1 as an output is for every element in the set a to be 1. We will cover this kind of 
testing of the algorithm more when we cover invariants. Since we are discussing Normal Forms, lets find the element that is the Normal Form for each of our
elements 'a'. The elements that are non-reducible by our reductions are the single bit values 0 or 1. Therefore, they are our Normal Forms. 

I'm sure for a reader with a modicum of understanding regarding logic, this has been a very easy to follow example. Let's examine why any of this is important in 
the context of software development. 

Following the idea that sets will always reduce to a specific *Normal Form*, we can quickly see that the order in which we apply our rules doesn't really matter. 
Take the above example for instance, which 11's we choose to reduce to 1's don't matter as we always reduce to the same *normal form* or set of *equivalence 
classes*. This idea is called the *Church-Rosser Theorem*, named after the mathematicians Alonzo Church and J. Barkley Rosser who penned the first formal proof 
of the theorem. 

Since haskell uses a form of lambda calculus, the Church-Rosser Theorem applies to it. From the Church-Rosser theorem, we can make some interesting observations 
about code that we write in haskell. Before we get there though, we need to understand something called *Outermost Reduction*. Informally, Outmost Reduction is a 
kind of function evaluation which always evaulates arguments prior to evaulating the recursive function definition. From the Church-Rosser theorem, we know that 
the order of reduction doesn't matter to us. However, from the perspective of termination, Outermost Reduction ensures termination if there is some normal form. 

In fairness, I'm not quite sure why. But all this information is important in orderstanding a broader topic which is Lazy Evaluation. An aspect of Haskell that 
seems to be almost as defining as its functional roots. 

I hope to write a blog post about Lazy Evaluation in the future to dig deeper into what it means and why it matters in the context of software development. Be on 
the lookout for that soon!

