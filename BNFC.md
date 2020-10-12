# BNFC (Blog Post 4) 
For our first assignment we used BNFC (Backus–Naur Form Converter) in order to generate our context-free grammar which we discussed in the previous blog 
post. 

I'd like to take some time to dive into the history, implementation, and formal definition of the Backus-Naur form in an attampt to better understand it 
holistically. 

Backus-Naur Form is a form that context free grammars may be written in which describe the necessary syntax or grammatical rules of a language. 
As part of Programming Assignment 1, we defined a context free grammar for several mathematical terms important to the functioning of a basic calculator

Let's consider a line found within that assignment: 

```
Times. Exp4 ::= Exp4 "*" Exp5 ;
```

Here we see am important *metasymbol* 
