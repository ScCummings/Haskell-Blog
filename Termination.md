# Rust and Ownership 2 (Blog Post 13) 

This blog post is a continuation of my previous blog post regarding the memory system and Ownership process of the programming language Rust. If you haven't already 
read that blog post (12), read that before continuing on. 

So consider the following Rust code: 
```
{
let dog1 = Dog::from("Fido",2,"pitbull"); 
}
{
let dog2 = dog1;
}
```
the prevously listed code describes the nonexistant class Dog that takes arguments String name, number 2, string breed. In memory, we would think that it is 
structured something like this: 
```
dog1 -> [0x0001] //memory address where the dog1 variable is stored
dog2 -> [0x0010] //copy of memory address 1 where the dog1 variable is stored.
```
Unfortunately, in actuality, the memory address looks something like this: 
```
dog1 -> [0x0001] //memory address of where the dog1 variable is stored
dog2 -> [0x0001] //the same memory address where the dog1 variable is stored
```
For those of you who have been following along closely, you may see the problem with this memory structure. If dog1 holds an *Owner* variable that calls the 
drop() function when dog1 falls out of scope, thereby freeing up the memory that held dog1 on the heap, and dog2 points to that same place in memory on the heap, 
when the program goes to instantiate dog2, it will encounter an error because that memory has potentially already been cleared and reallocated. 

Similiarly, if the code is written like this: 
```
{
let dog1 = Dog::from("Fido",2,"pitbull"); 
let dog2 = dog1;
}           [line 4] 
```
Once the code reaches line four, both dog1 and dog2 will pass out of scope. Because they fall out of scope, they will both call the drop() function meaning that 
the program will try to clear and reallocate the same memory twice. This is obviously problematic and is caled a *double free* error. 

Rust has an interesting work around for this problem though. When you assert one value to be the same as another i.e.: 
```
let dog2 = dog1;
```
it actually calls the drop() function on dog1 thereby removing it entirely from memory, meaning that you cannot access the contents of the dog1 value. 

Consider the hypothetical code below. Here the function bark() returns a string value depending on the breed of the dog: 
```
{
let dog1 = Dog::from("Fido",2,"pitbull"); 
let dog2 = dog1;

dog1.bark(); 
} 
```
This code would actually throw an error in the Rust system as the memory used to instantiate dog1 has been cleared at realloacted since we instantated dog2. 

While this is a neat workaround, I can't help but feel that it hinders more than it helps. Often times I may need a temporary value to store a variable but that 
doesn't mean I want to destroy the original value that I have. I am also curious then how Rust implements swapping variables if it doesn't use any temporary 
variables. 
