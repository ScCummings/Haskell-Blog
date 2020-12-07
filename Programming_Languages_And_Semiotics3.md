# Programming Languages and Semiotics 3 (Blog Post 18)

This final blog post will be dedicated to exploring the paper "Semiotics and Programming Languages linked below. If you haven't already read the first two 
Programming Languages and Semiotics blog posts (16 and 17 respectively), then I recommend going back to cover them as we continue our journey through the paper. 

Link: https://dl.acm.org/doi/pdf/10.1145/365230.365249?casa_token=vQoIiN5Vx4gAAAAA:imblU2qrUlhqlnGYbCrFFf38NwfS5DzGo-rBMXz_ZvlHDYVHf0WiL6Sj8TrpvjBQbYWWXKCNUtMV3xY

One defintion that came up earlier in the paper that I thought would not be largely important yet has shown up again and again is *formalism*. The main reason I 
haven't yet defined is that for awhile I wasn't quite sure what it meant. the paper does an excellent job of defining it about two thirds of the way in though. 

*Formalism*, as described by the paper, is the linguistic attempt to pack as much meaning into as few symbols as possible. Effectively, getting as much "bang" for 
you "buck" as possible. 

The paper gives an example of formalism in the form of plural words. Instead of making an entirely new word for more than one duck. I can just say the word duck*s* 
to indicate that I mean more than one. 

Mathematics to some degree is concerned heavily with implementing *formalism*. To the point where many symbols are shared across many different mathematical or 
scientific fields. 

Especially in introductory computer science, we are primarily concerned with replicating real-world mathematical or scientific models (which reminds me, check 
out my blog post on Julia if you haven't already :) ). Therefore, the philosophy of formalism is often applied to computer science as well. There is practical 
reason for this in programming languages, as the more there is to parse through, the more computational overhead may come with certain operations. 

A balance between strict adherance to *formalism* and readability is crutial in programming languages and broadly in scientific communication. 

We have previously defined *pragmatics* as a school of thought in the field of semiotics. What is interesting in the relationship between programming languages 
and semiotics is that the application of pragmatics changes so drastically. In anthrocentric semiotics, we are concerned with how a kind of rhetoric practically 
impacts the listener and how the listener interprets the subject of the speech. In mechanocentric semiotics (I have no idea if that is actually a phrase but we 
will use it now) the concern is on how certain machine language impact systems and more important (since is it more practical), what information we can glean 
about a system based on how it interacts with certain machine language. In the simplest form, some systems will not understand or interface with certain 
languages entirely, even at the hardware level. Operating systems may not accept instructions from certain processors or arthmetic logic units and so this 
interfacing of language and logic of hardware become essential to understand at the most basic level. 

The paper goes as far as to claim that the "interpreter" as is written about by Theophrastus is directly analogous to the compiler of a modern computer system. 
I'm not sure how accurate this analogy is though, as machine language can exist without a compiler to interpret it where natural language cannot exist without 
some hypotetical interpreter of the language. 

The paper quickly dives into this distinction and I'll do my best to provide some interesting commentary with it. 

+ *What do different translating principles/compilers do to the language?*

  So we actually have looked at this question in class on some level. We can think of Abstract Reduction Systems as kind of proto-translating principles. 
  Similiarly, we can think of different aspects of a programming language (functional vs. non-functional/content-addressed vs. non-content-addressed) as 
  contributing factors to how we interpret the language. For instance, my mind set when programming something that is object-oriented or C based is entirely 
  different than when I program something in haskell or a networked system in Java or JavaScript. I tend to focus more on lower-level logic when programming 
  haskell where as a C based programming session usually leaves me thinking about the interactions or abstractions of objects. 
  
  + *How do they influence the machine language (programs) and results?* 
  
  My haskell code tends to be considerably shorter yet tends to be rather beautiful in it's simplicity. It is nice to go from a class like *Data Communication* 
  where graphs and network structures must be parsed and sorted through to *Programming Languages* where our assignments tend to focus more on the structure of 
  our logic. 


