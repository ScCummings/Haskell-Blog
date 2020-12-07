# Linear Haskell 1 (Blog Post 14)

This blog posts will be my first blog post concerned with exploring and reacting to the content in the paper "Linear Haskell". The paper is rather long so I may 
need multiple blog posts to finish it but I will do my best to be thorough and analytical in my approach. 

Here is the link to the paper: https://arxiv.org/pdf/1710.09756.pdf

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
once. Different data types have different interpretations with regards to whether or not they have been "consumed". The first data type is referred to a an 
*atomic base type* a brief informal definition is provided below: 

+ *atomic operations or data types* - as far as I've been able to tell, atomic operations refer to computations that are can only be executed completely or not 
at all. In other words, the computer either performs the computation or not at all. Atomic data types are data types that are used only in atomic computations 
like ints or pointers. A computer cannot "half-add" two integers. It either adds them or it doesn't. Of course, there are components called half-adders but pay 
them no mind...

In the case of atomic data types, to constitute consumption, the data need only be evaluated. 

In the case of function types, apply it to a single argument and accept it's return value. For instance, the following function value is consumed exactly once: 

```
funt fact;
fact (int input){
  if(input == 0 || input == 1){
  return 1; 
  }
  else{
  return input * fact(input -1); 
 } 
}
```

+ In order to determine if a pair of arguments are consumed once, we first check to see if they are of the same type. If they are of the same type, and are both 
executed, then they are consumed exactly once. 

Similiar to how Rust has immutable Strings, the paper covers immutable arrays. They also provide a definition for mutable arrays that I won't include here for 
brevity's sake. Though an interesting things to note is that the paper's implementation doesn't include a new type for a mutable array but instead a function 
that updates array values and then returns the normal immutable array. 

An issue that the paper brings up that I wish it would cover in slightly better detail is how this implementation leads to *unsafeFreeze*. As far as I can tell, 
this occurs because there is no new copy of the array to look to. It is not exactly well explained though linear data types are supposedly able to solve this 
unique problem to arrays. 

The topic was fairly interesting though I fear that I am not quite knowledgeable about theoretical computer science to the degree to which I would need to be to 
best understand the paper. 
  

