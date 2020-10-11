# Recursion & Functional Programming (Blog Post 1)
The following blog was created in accordance with the assignment specifications for the course *CPSC 354: Programming Languages* taught at Chapman University. Its primary purpose is to act as a kind of guide and journal as I learn the programming language Haskell as well as the underlying logic and conceptual frameworks that make it a valuable tool. 

**Recursion**

Consider for a moment any shape that has repeating shapes within it. I immediately think of a golf ball. Golf balls have dimples along their bodies in order to generate turbulance in the air as they fly. This turbulance decreases drag and allows for a farther distance to be travelled. 

Imagine you are put in charge of manufacturing these golf balls. How would you determine where and at what depth you would carve the dimples? For the sake of simplicity, lets say you have a mold of the dimple that will fit the surface area of the ball so long as it is evenly spaced. The more intuative thing to do would be to pick on point on the ball, create a dimple, and then create six other hexogonal dimples around the first one. Then, starting in the right hand corner and moving clockwise, adding dimples where there are none until the entire ball is covered in evenly spaced dimples. 

For a visual aid, I created some images to help the reader think through this process. 

https://drive.google.com/drive/folders/1Z2IOAxIAiw2uuiEoq0cNkGFKUu6IuIq-?usp=sharing

In these images, the red dot indicates the current point on the ball we are considering and the numbers indicate the order in which we create dimples. 

If we attempted to program this process using some iterative programming languages [^1], the code may look something like this: 




The following examples will use C++ code to explore how Haskell differs from other, what we will call imperative programming languages however you could just as 
easily use Python, Java, or any others. 

[^1]: An iterative programming languages is simply a language that uses various kinds of loops to repeat over instruction sets. Haskell, the language we are using, is not iterative and is instead functional, or written as it would be in mathematics. 
