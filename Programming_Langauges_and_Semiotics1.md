# Programming Languages and Semiotics 1 (Blog Post 16)

My idea with these last few blog posts is to delve into the history of programming languages and how they have interacted with the culture, scientific 
advancements, and events that shaped the times that they were created in.

The first programming language created that actually had an associated compiler was created by Corrado Böhm in 1951 for his Dissertation. I actually wanted to 
perhaps write a blog post about it though quickly ran into the issue of not being able to speak French. 

Having scrapped that idea, I searched through the early histories of programming languages in order to find something worth exploring in detail. The paper I 
settled on certainly has historical value, but also focuses on an interestingly related subfield of communication, semiotics. 

Semiotics is loosely defined as the study of signs and symbols. Since symbols are prevalent in and unique to human communication, it is understandable that many 
disciplines would take an interest in the field. Even over the Summer when I took a communication course to fulfil a general education requirement, I read 
semiotics papers assessing Natural Language Processing techniques and organiation. 

The paper is linked here and I will do my best to break down its contents either in one or two or three blog posts: 
https://dl.acm.org/doi/pdf/10.1145/365230.365249?casa_token=vQoIiN5Vx4gAAAAA:imblU2qrUlhqlnGYbCrFFf38NwfS5DzGo-rBMXz_ZvlHDYVHf0WiL6Sj8TrpvjBQbYWWXKCNUtMV3xY

The paper begins with a bried albiet interesting foray into European History though it is not entirely necessary for our understanding of the paper's 
applications to programming languages so we will skip it here. It then covers Charles Morris, an American scholar who "founded" the field of semiotics. I put 
founded in quotation marks as arguably many of the concepts and philosophies of the discipline existed in outside fields such as linguistics, sociology, and of 
course mathematics from Oxford scholars to Mandé griots. 

Never the less, Morris chose to divide the discipline into three distinct categories: 
+ *Pragmatics* - the study of the relationship between symbols or signs and those who consume or interpret them. The paper references a student of Aristotle, 
Theophrastus who claimed that all speech (in our case communication) was both about how it was interpreted by humans but also impacted the things which is was 
talking about. Granted, I'm not a philosophy student, but this seems a strange case to make. If I present a paper on Haskell, that does not change Haskell, 
though it may change how people interpret it. Regardless, Pragmatics are a bit outside our lens as computer scientists so we will put it down for now. 

+ *Semantics* - The study of the meaning of signs and symbols. This is fairly important within the context of programming languages because we want to make sure 
we are describing the same logical processes. The paper does not cover this relation though it is of interest so I will briefly cover the forms of semantics as 
they relate to programming languages. *Operational Semantics* defines the meaning of a set of symbols to be the computation it runs. This doesn't necessarily 
have to do with the structure of the language but moreso the design philosophy behind it. A program's security, efficacy, and correctness are determined by 
assessing the instructions that the program executes and those instruction's effect on the data. *Denotational Semantics* are concerned with mathematical object 
and relationships that represent a program's effect on a data set. A program's security, efficacy, and correctness are determined by assessing the mathematical 
phenomenon that is being undertaken rather than on the individual instruction level. *Axiomatic Semantics* is based loosely on Hoare Logic and effectively looks 
to changes in the state of variables to determine a program's security, efficacy, and correctness. These changes in the state of variables are described as 
assertions. As we can see from these brief desciptions, Semantics can have very real effects on programming languages and how we interpret them. 

+ *Syntactics* - Where we get the word *Syntax* from. Syntactics describe the relationship between symbols. Consider the following code: 
```
int x = 5;
add 5 &2 &3
```
The above two lines may appear very different, though semantically they are the same. Syntax is very important to the functioning of a programming language in 
that it describes how the language will look and be read by software engineers. Considering the fact that code bases are constantly in need of renovation or 
redeployment, studying ways to make programming languages more readable by engineers is a necessary time saving strategy. 

Check out my next two blog posts 17 and 18 to continue exploring the paper linked above!


