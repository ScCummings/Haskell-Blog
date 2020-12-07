# Modeling Pandemics in Julia 1 (Blog Post 15)

My intention with this blog post is to react and reflect on the video "JuliaCon 2020 | AlgebraicJulia: Applied Category Theory in Julia | James Fairbanks" as well 
as to connect various aspects of the video with topics we have covered as part of our course. 

Here is a link to the video: https://www.youtube.com/watch?v=7zr2qnud4XM&feature=youtu.be

The presenter begins by presenting a spectrum of scientific tools. On one end you have *arbitrary code*. This is what software engineers primarily work in. It is 
a representation of a real world or imaginative system. For instance, when computer science students take *data structures and algorithms* and they program the 
*game of life* they are merely writing code to replicate some arbitrary system. This is incredibly helpful and is likely why many of the other sciences require 
one or two courses in computer science. Given you can model almost anything as abstract code, it becomes invaluable to scientists concerned with physical 
applications and computer driven simulations. 

On the other side of the spectrum are *Computer Algebra Systems* which explicitly represent real world phenomenons (like physics or epidemiology) as mathematical 
models or expressions. 

In the middle there are *Modeling Framworks* which combine the two. In other words, they have explicit models and representations of the phenomenon while also '
computing real would values that would be helpful in the study of that phenomenon. 

I have used many of these modeling systems already in my career at Chapman. Hardware design suites such as *Vivado* could certainly be considered as well as more 
physics based applications like *lumetri*. 

The remainder of this blog will be dedicated to exploring and assessing the *layers of GAT based modeling* laid out in the presentation. 

First and foremost, what is GAT based modeling? The presenter does very little to introduce it, that being said, I believe it to be an acronym for *Graph 
Attention Network* and as you can see, there are some interesting connections between the layers presented and the graph data structure. 

In GAT based modeling, the programer takes three steps: 
+ In the first step, *Theory*, the programmer lays out the fundemental relationships and logic of whatever phenomenon they are trying to study. It may be boolean 
logic and algebra for a circuit design modeling application or differential equations for an epidemic centered modeling application. 

+ In the second step, *Syntax*, the programmer continues developing their understanding of the mathematical models. First, they define their model in terms of 
*Formula Notation*. This may seem rather similiar to the *Theory* section, however the core difference is that in the *Theory* section, the programmer is 
defining their model with regards to *universal algebra* or *general algebra* and in the *Formula Notation* sub-section, we are primarily concerned with defining 
our mathematical models in terms of higher order math logic and symbols. On other words, we are writing it as we would write it to explain it to a mathematician. 
The next sub-step in the *Syntax* layer is the *Wiring Diagram* where we physically map out our mathematical model. In the previous example of a digital logic 
modeling application, the *Wiring Diagram* wouldn't literally be a wiring diagram but a map of how the different aspects and variables of the mathematical 
phenomenon interact. In the instance of epidemiology, the wiring diagram may be a series of vectors that describe mitigating and agrivating factors like wearing 
masks, social distancing, or washing your hands. The final sub-step in the *Syntax* layer is developing an *Embedded Domain Specific Language*. In the context of 
this course, this is perhaps the most interesting step. It is developing libraries, functions, and aspects of programming languages that will be helpful in the 
study of whatever mathematical phenomenon you might be studying. In the context of our hypothetical digital logic modeling system, we might write code for 
building basic components like AND or OR gates using CMOS transistor bulding blocks. In the context of epidemiology, we might write code for assessing vectors in 
the patients like age, income, and geographical location. 

+ The final step of GAT based modeling is the *Instance* layer. This is probably the easiest to understand and most practical layer. It is concerned with 
translating that *Formula Notation* into pure Julia code and performing the necessary computations to run it. 

The talk then gets into a little bit more technical detail with regards to Julia and how it allows for the creation of more functional, mathematically based 
models than other programming languges. I have focused a lot of my past blogs on assessing haskell-adjacent programming languages and so I will skip this piece 
at least for this blog post and decide if I need to continue a dive into the language for a future post. 



