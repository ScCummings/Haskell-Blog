# BNFC (Blog Post 4) 
For our first assignment we used BNFC (Backus–Naur Form Converter) in order to generate our context-free grammar which we discussed in the previous blog 
post. 

I'd like to take some time to dive into the history, implementation, and formal definition of the Backus-Naur form in an attampt to better understand it 
holistically. 

Backus-Naur Form is a form that context free grammars may be written in which describe the necessary syntax or grammatical rules of a language. 
As part of Programming Assignment 1, we defined a context free grammar for several mathematical terms important to the functioning of a basic calculator

**Implementation**
Let's consider a line found within that assignment: 

```
Times. Exp4 ::= Exp4 "*" Exp5 ;
```

Here we see an important *metasymbol* "::=". Existing since the advent of the Backus-Naur form, this symbol is read as "is defined as" and existed since 
the advent of the form. 

Another important metasymbol not located within the line are the "<>" lines. These symbols would indicate where the set of symbols considered the 
expression would be located. In other words, we would rewrite the previous line of code as: 

```
<Times. Exp4> ::= <Exp4> <"*"> <Exp5> ; 
```

Thankfully, with newer versions of the converter, this is no longer required. 

**History**

Peter Naur and John Backus are the engineers for which the form was named though a lot of the understanding of the form can be drawn from a 1963 report by 
Naur called ALGOL 60. 

One important aspect of BNFC or rather the history of BNFC that I want to touch on is the idea that truly this form is merely a way to define context-free
grammars. In the previous blog post I explained that 

 
 
