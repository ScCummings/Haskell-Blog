# Rust and Ownership (Blog Post 12)

This blog post will cover introductory topics for the programming language rust and Ownership, a unique aspect of the language. It will be similiar in structure to 
my posts on Unison in terms of sticking to abstract notions of the language as opposed to practical applications. I take this approach as I believe it has more 
educational value to me. Learning the aspects of these languages and how they differentiate themselves is probably more valuable than the experience of programming 
in them and learning their syntax. 

Rust's website begins by explaining the *garbage collector* an aspect of many programming languages, including (unless I am mistaken) Java. The general idea is that 
the program constantly scrubs the computer for new memory to use. 

Other languages, most notably C++ (unless I am mistaken) allow and require the programmer to allocate memory explictly through the use of pointers. Supposedly, Rust 
uses neither of these systems and instead ops to use the system of *Ownership*.

Rust's website goes to great lengths to explain the *stack* and the *heap* because they are closely tied to the process of *ownership* I could explain these 
concepts but truthfully they aren't terribly important and a little simplistic to be the subject of a blog post. If you're confused on how the *Stack* and the 
*Heap* work, the rust website does an excellent job of spelling out exactly how they function. 

Listed here are the rules presented that allow for Rust to use the process of *Ownership*. 
+ Every value in Rust, whether it be a string, int, or other data type, as an associated variable called its *owner*. 
+ Each value can only have one owner at a time. 
+ When the owner is out of scope the value is dropped or not computed. 

Scope is also a tad bit trivial to be the subject of a blog post as it would normally be covered in an introductory computer science or object-oriented 
programming course. That being said, I will briefly note here that Rust defines scope as purely any variable defined within {} regardless of whether it is a 
class or function. The website provides an example but I will write my own here: 

```
{                                             //iterator is out of scope here because it hasn't been defined yet
     let string = "Hello World";              //iterator hasn't been defined yet so it is still out of scope.
     let iterator = 0b001_0010i64;            //iterator has now been defined so it is in scope
        
     assert_eq!(iterator.count_ones(), 1);    //iterator is still in scope. 
}                                             //our {} have now closed so iterator is once again out of scope. 
```

Applying this to our previously touched on rules of *Ownership*, we can see that the value "Iterator" is in scope in the verified spaces but it also has a valid 
*owner* and therefore can be a part of the memory system of *Rust. 

Rust's website then descibes their String function, since it illustrates a bit more of the thought process beind memory allocation for programming languages, I 
will cover the main ideas here as well as some brief asides. 

The String data type is stored on the heap rather than the stack because it is mutable. In other words, we will want to change the value at some point and 
therefore it is more convenient to keep in the heap. In any program that accepts user input, this would be necessary. Since they are unknown at compile time, we 
must allocate some small piece of memory for them later down the line. That's why in general, when possible, hardcoding strings as *string literals* is more 
preferable than using the actual string type. 

When rust instantiates the String type, it allocates that small piece of memory it needs automatically. This isn't exactly unique to Rust though and happens in 
many programming languages. 

Returning that memory is usually performed by that *Garbage Collector* that we referenced earlier. Its job is to scrub and find when free memory comes up. Rust 
has that *owner* variable though. So when the owner goes out of scope, we can know that the value can be returned to memory. A neat trick for figuring out when 
and where to quickly get memory back. My one concern would be how much computational overhead is paid to keep track of the owners as an extra value of the type. 

This idea of keeping variables to track when a value should be removed from or given memory isn't exactly new, though no ideas trully are. In C++, the idea is 
called *Resource Aquisition Is Initialiation (RAII)* 

In object oriented programming, the variable that keeps track of the memory lifetime is instantiated by the constructor of the class. What is useful about this 
implementation is that if there isn't enough memory to properly instantiate the object, the code will merely not create the object. This is preferable to 
tracking through null pointer exceptions to find a memory leak in the code. Though I am not sure why programming languages don't throw memory errors at that 
point though. 

This topic has certainly been interesting and I like it about as much as I did Unison so I will likely write another blog post on this programming language and 
its implementation. 


