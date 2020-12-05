# The Y Combinator (Blog Post 9)
 
 We covered the Fixed Point Combinator briefly in class but I would like to write a blog post on it both as a way to 
 review but also as a way to dive a little deeper into the subject to better understand both it's application in 
 theoretical computer science as well as software engineering. 
 
 This Blog post is also loosely based off of the excellent video by the Computerphile youtube page. Here is a link to 
 the video: https://www.youtube.com/watch?v=9T8A89jgeTI
 
 How might you logically describe *recursion* without the use of recursion? The first time I heard the term 
 *recursion* was actually before I had ever even written a program. In high school I went to a history summer camp
 (riveting I know) and took as many of the Art History courses as I could. I loved the art of the 20th century and 
 focused on that era when doing research. A favorite artist of mine, M.C. Escher, would often create art that was 
 referred to by my textbooks as recursive. I wouldn't hear the term again for another 
 two year when I took an object-
 oriented programming course. 
 
 While envisioning M.C. Escher's paintings certainly creates a vivid way of 
 remembering recursion, let's try to 
 define it in terms of lambda calculus, a way of describing functional logic that we 
 use quite a lot in this course. 
 For any reader who is perhaps a little behind the curve on the fundamental of lambda 
 calculus, I highly recommend
 going back and reading my blog post about it. 
 
 So, Thinking in terms of lambda calculus, to find a term that reduces to itself can 
 be fairly trivial. 
  ```
 \x. x x \x. x x
 is parsed as-> 
 \x. x x (\x. x x)
 reduces to-> 
 \x. x x \x. x x
 (lambda calculus encoding of looping) 
 ```
 The above lambda calculus allows for looping as we would think of it as average software engineers, but not necessarily resursion. To encode recursion in lambda 
 calculus is a bit more complicated. The above linked video describes a function called "rec" which is the simpliest recursive function which would could think 
 of in terms of software engineering as *general recursion*. The video provides a handful of exercises which I will complete below as well as a few of my own. 
 
 They formally define rec as: 
 ```
 rec f = f(rec f)
 ```
 The first excersise is to define the previous looping function in terms of rec: 
 ```
 loop = rec(x) 
 ```
 
 The second is to define factorial in terms of our "rec" function and lambda calculus 
 ```
 fac n = rec(\f. \n. 
            0 -> 1
            x -> n-1
 )
 ```
 This may look strikingly similiar to some of the code that we wrote for assignment 3 for this class and that makes sense. And this makes sense. Once we can 
 learn how to encode *general recursion*, we can add it into any programming language that we define regardless or whether or not the implementation natively
 exists. 
 
 Now let's take a look at defining our rec function solely in terms of lambda calculus: 
 ```
 rec = \f. (\x. f(x x)) (\x. f(x x)
 ```
 It looks eerily familiar right? That is because it is encoding recursion rather than looping but the two processes are fairly similiar. We are still replacing 
 some function with itself as we would want to do for any recursive function. 
 
 
 
 
 
