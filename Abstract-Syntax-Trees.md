# Abstract Syntax Trees and Context Free Grammar

This blog post will cover a lot of what was already discussed in class while going further into the formal definition and history of context free grammar.
A lot of the structure of the blog is based on the first lecture from the *Parsing Algorithms* series of videos from the YouTuber Dmitry Soshnikov of course
with my own examples and analysis. His channel is linked here and has been a great resource for my own learning: 
https://www.youtube.com/c/DmitrySoshnikov-education/featured

So up until now we've dived into recursion as well as functional programming, which are very important concepts in the grand goal of understanding how
programming languages are created, but let's go into a topic even more integral to the process: 

Consider the algebraic expression: "x = y + 2 * 3" 
This simplifies to, "x = y + 6" 

Assume for a moment that y is a variable for which we have a value. This means that we can solve for x. This blog post will step through basic parsing 
of an instruction as well as the creation of an abstract syntax tree. 

*Tokenizers*

The expression first passes into a Tokenizer whose role is to perform lexical analysis. In other words, the tokenizer breaks the expression down into tokens
or distinct sets of characters and variables defined by the grammar. In our case, we will end up with a set of tokens like such: 
```
{"x","=","y","+","2","*","3"}
```
This set of tokens are then passed into a parser. The exact functioning of this parser is somewhat complicated and can be done a number of ways however,
after it's running we should be left with an Abstract Syntax Tree: 

       assign
      -      -
     <        >
    x          +
              - -
             <   >
            y     *
                -   -
              <       >
             2         3
             
Working from the bottom up, we can see this makes a lot of sense. You start with multiplication, as you would with normal order of operations, then work 
to multiplication, before finally ending with the assignment. The parser here is performing syntactic analysis, creating the tree based on the context 
of the symbols that separate our other tokens. 

Now that we understand this basic concept, let's define some important terms for further discussion. 

**Alphabet:** A set of all possible symbols used.
**Language:** A set of all combinations of symbols contained within an alphabet. Inherently infintitely large without a grammar. 
**Grammar:** A set of restrictions on the language that decreased the size of the language. 

Grammars are sets as well and there are a few aspects of them that are important to discuss before coming to Context Free Grammars. 
**Non-terminals** within the context of grammars refer to symbols which represent other values. For instance, in mathematics, the varaible x is 
non-terminal as we can likely simplify it to some other value through algebra. 

**terminals** intuatively, terminals are values that are the end of a string of possible representations. Integers may be considered terminals as there is
no more simplistic way to represent the value 2 other than "2". 
         
Noam Chomsky, who I never thought I would be discussing in a computer science class, wrote of a grammer hierarchy that separately certain kinds of 
grammars from others. 

At the zeroth level there are **unrestricted or natural languages**. Certainly there are rules though context, tone of voice, nonverbal cues, and all 
manner of other indicators impact how the meaning of the phrase is determined. 

At the first level there are **context sensitive languages**. These may be talked about as most programming languages or basic mathematical expressions
In other words, there may be any combination of terminals and non-terminals on either the left or right hand side of an expression. 

Then we get to **context-free grammars** an important topic of this course which has a few important distinctions from context sensitive languages. 
Namely, there is no context on the left hand side of the expression and there can only be one symbol, that symbol must be nonterminal. 
