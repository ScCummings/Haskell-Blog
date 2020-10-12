# Abstract Syntax Trees and Context Free Grammar

This blog post will cover a lot of what was already discussed in class while going further into the formal definition and history of context free grammar.
A lot of the structure of the blog is based on the first lecture from the ~Parsing Algoritms series of videos 

So up until now we've dived into recursion as well as functional programming, which are very important concepts in the grand goal of understanding how
programming languages are created, but let's go into a topic even more integral to the process: 

Consider the algebraic expression: "x = y + 2 * 3" 
This simplifies to, "x = 6y" 

Assume for a moment that y is a variable for which we have a value. This means that we can solve for x. This blog post will step through basic parsing 
of an instruction as well as the creation of an abstract syntax tree. 

*Tokenizers*

