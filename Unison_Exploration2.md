# Unison Exploration 2 (Blog Post 11)

This blog post is a continuation of my previous blog on Unison exploration. It is loosely based on the link provided to us in the programming languages github as well as on a talk given by cocreator Rúnar Bjarnason. 

Here is a link to the talk: 
https://www.youtube.com/watch?v=rp_Eild1aq8

Another issue that Unison supposedly solves is something affectionately called *Dependancy Hell*. I imagine this to be issues that arrise as one program relies on 
another for defintions. This occurs commonly in many forms as a part of object oriented programming. One class is extended from another and so on and so forth until 
you have a complicated, interwoven structure of classes that each relie on another. 

When I was in *Data Structures and Algorithms* I remember many a sleepless night in front of the visual studio debugger trying to sort exactly where my code was 
running into issues. The above example though is less relevant to our discussion of Unison though as Unison solves the problem of dependancies with respect to 
libraries of code. The only time I have directly worked with a library of code was when I worked in the .NET framework for C#. 

Specifically, Unison tracks which functions other functions depend on on an individual basis. If you function only uses one other function from a library, the 
entire library doesn't need to be compatible in order for you to use that function that you depend on in your code. The reason why it can do this is once again 
related to the hash codes that Unison generates for functions. Because functions can be stored in such a simple way, their dependancies can also be stored and 
granularly extracted from libraries that contain them. 

Another interesting aspect of Unison is that it focuses on providing error messages that are easy to read and understand. Bjarnason says that he intends for 
error messages to read like another developer explaining to you the problem with the code. When we first began programming in Haskell, I was very impressed with 
their error messages. Mismatched types were spelled out and it was relatively easy to figure out where the problem was. 

Unison takes this philosophy to another level though, solving trivial problems for the software engineer. Bjarnason gives the example of an ambiguous function 
name. To expand on what he said though, imagine for a moment that you have two different functions "foo" whose defintions are different. When you call the 
function foo, Unison will simply select which function is of a type that is called for. It can do this once again because of the content addressed hashing that 
occurs when you define a function in Unison. If the ambiguously named functions are all of the same type, the error message will actually present all other 
alternative functions that fit the type you are looking for, kind of like a quick and easy reference for other locally defined functions that you would be likely 
to want to use. 

This process of searching locally defined funtions of the correct type reminds me of spatial locality in cache memory. There, data that physically near recently 
accessed data is cached for ease of access. 

A slightly less interesting and more complicated aspect of Unison programming is its use of nodes. Not necessarily analogous to their networking counterparts, 
nodes are spaces where computations take place. If you remember my first blog post about Unison (If you haven't checked it out then you should), you'll remember 
us discussing how the hashing feature of unison code allows for us to deploy the same code with the same implementation on any computer with Unison. Nodes can be 
thought of as separate instances of running Unison that all have access to the code base that you are working on. 

You can define at which remote node you would like to execute a specific function as well. 

For instance: 

I can define a function toString using the following syntax: 
```
toString-at: Node -> Text -> Remote Text
```
where "toString" is the name of the function, "Node" is the starting type (as far as I have seen in Unison code, all functions start as type Node, "Text" is the 
type that is generated when you run the function, and "Remote Text" is the type that is generated when you run it on a remote node as you usually would. 

You can then run the program on a remote node using the following syntax: 
```
toString-at ourNode n = 
at ourNode (Remote.pure {toString n})
```
Where "toString is the name of the function we would like to call, "ourNode" is the name of the node we would like to execute it on, "n" is the function argument 
(i.e. the thing we want to turn into a string), "Remote.pure" is just an ability specifying that we are executing the function remotely, and "{toString n}" is 
the normal way we would execute that function if we were not doing so remotely. 

I deeply enjoyed reading and researching Unison and hope at some point to be able to contribute some code to it. I also joined their alpha testing slack to learn 
more about the language! Thanks for the suggested reading!





















