# Linear Haskell 1 (Blog Post 14)

This blog posts will be my first blog post concerned with exploring and reacting to the content in the paper "Linear Haskell". The paper is rather long so I may 
need multiple blog posts to finish it but I will do my best to be thorough and analytical in my approach. 

The paper begins with a series of definitions, many of which become important later in the paper. Two of particular interest to us are: 


+ *linear* - which is used to describe a function which only comsumes it's function once. An example of a linear function could be something like this: 
```
float squareRoot(int radicand) {
radicand.pow(1/2)
}
```
since the radicand is only consumed once. 


+ a *linear arrow* is a symbol designed to indicate that a function is linear: 
```
f::s->t
```
The above function guarentees that any function call of the function f will be linear in nature and that any argument u of the function f will be consumed only 
once. Different data types have different interpretations with regards to whether or not they have been "consumed". The first data type is referred to a an *atomic 
base type* a brief informal definition is provided below: 

+ *atomic operations or data types* - as far as I've been able to tell, atomic operations refer to computations that are can only be executed completely or not at 
all. In other words, the computer either performs the computation or not at all. Atomic data types are data types that are used only in atomic computations like 
ints or pointers. A computer cannot "half-add" two integers. It either adds them or it doesn't. Of course, there are components called half-adders but pay them no 
mind...


