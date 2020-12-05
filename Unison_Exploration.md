# Unison Exploration (Blog Post 10)

The purpose of this blog post is to document my exploration of the Unison programming 
language as well as some of it's most interesting implementations with regards to its 
unique *content-addressed code*. 

I'm going to be frank. I'm still not entirely sure what exactly "content-addressed 
code" means, but we're going to do our best to discuss interesting implementation with 
regards to it. 

Unison operates in terms of *Code bases* which as far as I've been able to tell are
collections of definitions and programs that use those definitions, though a formal 
definition is not provided. 

Unison's website begins by explaining the nature of the code bases as *append-only* 
meaning files are not directly modified or deleted. Their names are determined based on
their content which means that since you can never delete a file or part of a file from 
a build and cannot rename files directly, there can never be pipeline conflicts. while
I certainly hate sorting through merge conflicts especially as they seem to only happen
at the most inconvient moments, I'm not sure if the benefits outweigh the detriments in 
this case. I will keep working through the quick start guide though. 

You can formally define type signatures just as you would in any object-oriented 
programming language 
