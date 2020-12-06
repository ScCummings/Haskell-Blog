# Unison Exploration (Blog Post 10)

The purpose of this blog post is to document my exploration of the Unison programming language as well as some of it's most interesting implementations with regards 
to its unique *content-addressed code*. 

I'm going to be frank. I'm still not entirely sure what exactly "content-addressed code" means, but we're going to do our best to discuss interesting 
implementation with regards to it. 

Unison operates in terms of *Code bases* which as far as I've been able to tell are collections of definitions and programs that use those definitions, though a 
formal definition is not provided. 

Unison's website begins by explaining the nature of the code bases as *append-only* meaning files are not directly modified or deleted. Their names are 
determined based ontheir content which means that since you can never delete a file or part of a file from a build and cannot rename files directly, there can 
never be pipeline conflicts. whileI certainly hate sorting through merge conflicts especially as they seem to only happen at the most inconvient moments, I'm not 
sure if the benefits outweigh the detriments in this case. I will keep working through the quick start guide though. 

You can formally define type signatures just as you would in any object-oriented programming language by using the following syntax: 
```
base.List.file : [x] -> x
```
Where file is the object which you are defining the type for and [x] -> x is a the specific type. 

One of the cofounders of the company *Unison Computing* which of course creates the Unison programming language described it as "Superficially similuar to Haskell" 
which is definitely interesting as beyond their functional roots, Unison has many other features that distinugishes it from Haskell. 

One of these features that I found most interesting was how Unison is able to communicate
directly with other Unison nodes or locations, sending syntax trees for functions. 

Part of the issue with the following assessment of this feature of Unison is that I 
do not necessarily understand everything there is to understand about compilers, 
distributed network systems, etc. and so there might be some assumptions that I make 
that are incorrect. 

As far as I can understand, when you write a program in Unison, you can name it however you'd like in order to better understand it. Unison cares very little 
about this function name though, instead it identifies the program and it's type by a generated hash code of it's definition. 

How exactly this hash code is generated is a bit beyond me and probably proprietary but maybe it is similar to how we generate MIPS commands when writing 
assembly code. Where some hexadecimal (though I believe Unison uses decimal) value perhaps represents which instruction we are using or which register (in 
Unison's case it would be a location node) we are writing to and from. 

What is really cool about this sending of a hash code is that on the location node where the hash is being sent, they likely have the ability to determine the 
function and its type from the hash code, effecitely allowing for any computer with Unison to run any Unison code without any of the sticky networking 
connections that would normally be required.

One of Unison's cofounders Rúnar Bjarnason gives an analogy that really helped me better understand this concept. He says that Unison functions are like stars in 
the night sky. They always exist and are immutable, but we can always give them new names to better use them as tools. What this means is that we can quickly and 
easily send code across vast distances and it will run without any problems. Perhaps more impressive, in my eyes, is that unison code will be written in the 
exact same way two decades from now as it is now. Functions are immutable across space. This is incredible considering the amount of time that industry computer 
programmers spend going over outdated code or systems. If Unison catches on and begins to be used by major companies, that could save quite a bit of time in the 
future.  

What is also nice about this Hash naming function is that changing the name of a class or function is performed locally and changes nothing about the 
computation. I've worked on too many a game development project where a programmer decides to rename a specific function or corutine which necessitates a need to 
update all code in the project to match. You wouldn't need to worry about that any longer. 

These hash codes also explain my earlier confusion with merge conflicts. Say for instance that a programmer decides to slightly alter the definition of a 
function. Then locally she would generate a new hash from that definition. She could then push that to her branch and everything works well. No two files are 
being merged together, instead that old defintion will always still exist as a hash code though it may be replaced by the new defintion if the code calls for it.

I've decided that Unison and it's differences with Haskell are interesting enough to justify two blog posts so I will soon post a follow up to this one. 
