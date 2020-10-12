# Abstract Syntax Trees and Context Free Grammar

This blog post will cover a lot of what was already discussed in class while going further into the formal definition and history of context free grammar.
A lot of the structure of the blog is based on the first lecture from the *Parsing Algorithms* series of videos from the YouTuber Dmitry Soshnikov of course
with my own examples and analysis. His channel is linked here and has been a great resource for my own learning: 
https://www.youtube.com/c/DmitrySoshnikov-education/featured

So up until now we've dived into recursion as well as functional programming, which are very important concepts in the grand goal of understanding how
programming languages are created, but let's go into a topic even more integral to the process: 

Consider the algebraic expression: "x = y + 2 * 3" 
This simplifies to, "x = 6y" 

Assume for a moment that y is a variable for which we have a value. This means that we can solve for x. This blog post will step through basic parsing 
of an instruction as well as the creation of an abstract syntax tree. 

*Tokenizers*

The expression first passes into a Tokenizer whose role is to perform lexical analysis. In other words, the tokenizer breaks the expression down into tokens
or distinct sets of characters and variables defined by the grammar. In our case, we will end up with a set of tokens like such: 

{"x","=","y","+","2","*","3"}

