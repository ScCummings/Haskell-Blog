# Recursion & Functional Programming (Blog Post 1)
The following blog was created in accordance with the assignment specifications for the course *CPSC 354: Programming Languages* taught at Chapman University. Its primary purpose is to act as a kind of guide and journal as I learn the programming language Haskell as well as the underlying logic and conceptual frameworks that make it a valuable tool. 

**Recursion**

Consider for a moment any shape that has repeating shapes within it. I immediately think of a golf ball. Golf balls have dimples along their bodies in order to generate turbulance in the air as they fly. This turbulance decreases drag and allows for a farther distance to be travelled. 

Imagine you are put in charge of manufacturing these golf balls. How would you determine where and at what depth you would carve the dimples? For the sake of simplicity, lets say you have a mold of the dimple that will fit the surface area of the ball so long as it is evenly spaced. The more intuative thing to do would be to pick on point on the ball, create a dimple, and then create six other hexogonal dimples around the first one. Then, starting in the right hand corner and moving clockwise, adding dimples where there are none until the entire ball is covered in evenly spaced dimples. 

For a visual aid, I created some images to help the reader think through this process. 

https://drive.google.com/drive/folders/1Z2IOAxIAiw2uuiEoq0cNkGFKUu6IuIq-?usp=sharing

In these images, the red dot indicates the current point on the ball we are considering and the numbers indicate the order in which we create dimples. 

If we attempted to program this process using some iterative programming languages [^1], the code may look something like this: 

class node (bool flag_dipple, Node[5] adjacentNodes){
  flag_dipple = false; 
}

void fillNodes(Node currNode){
  for each Node in adjacentNodes{
  flag_dipple = true; //Fill (create a dimple) in every adjacent Node
  }
    for each Node in adjacentNodes{
    currNode = Node; //Select an adjacent Node
    fillNodes(currNode); //Repeat the process with that adjacent Node as the current Node
    }
}

This lengthy example is meant to explore the uses for and logic of recursion. **At it's most basic level, recursion is an event or function that recurs 
multiple times**. In the case of the golf ball, the filling of adjacent nodes from a current node occurs recursively. Inside of the function for 
fillNodes, we call the funciton fillNodes. You may have noticed a flaw in the program. Mainly, the golf ball would continue to create dimples forever as there is no checking of states to stop the process. Another issue is that the program is relatively slow, with a time complexity of O(n^2). 

Think for a moment of how you would do this process if there was no computer involved, just you and a knife. You might look at a spot on the golfball, 
carve out a dimple, then shift slightly, check and see if there was a dimple, and if not continue. For the sake of this example let's assume that spots 
on the ball have indexes and contain a value: dimple or no dimple. 

fillDimple(ball[n]) = true //for any index on the ball, create a dimple
fillDimple(ball[S(n)]) = fillDimple(n)//for any index on the ball, create a dimple for all previous indexes

This is incredibly simpler than our previous code but is accomplishing the same task. Granted, in our functional programming example (the one directly
above), we have indexes to represent spots on the ball, but the point is still fairly clear, **funcitonal programming languages such as Haskell allow us 
to deal with recursion in much simpler terms**. 

[^1]: An iterative programming languages is simply a language that uses various kinds of loops to repeat over instruction sets. Haskell, the language we are using, is not iterative and is instead functional, or written as it would be in mathematics. 
