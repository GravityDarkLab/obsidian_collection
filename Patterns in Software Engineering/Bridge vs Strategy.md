The strategy pattern proposes splitting out a class's algorithms into distinct classes referred to as strategies. To harmonise the implementation across all of the strategies, they will all use one same interface as a template. The context class must then include a reference to the Interface and initialise it in accordance with the desired strategy for this to function. The good thing about the Strategy Pattern is that we can switch between different Algorithm at run time. (The client will only have access to the context class.  
As an example will be the Creation of 3 classes: Add, Subtract and Multiply. Those 3 classes, that represents 3 different strategies, will implement the interface Operation. Now The context Class will have a variable of Type Operation that will be initialised accordingly to switch between the different algorithms following the needs.  

--> It s a Behavioural Pattern.  
  
The Bridge Pattern Decouple an abstraction from its implementation so that the two can vary independently.  
Here the Client will have access to an Abstraction that uses an Implementation. from this Implementation different Object will be defined.  
At the first glance Bridge Pattern seems to be the same as the Strategy Pattern, but the difference is that in the Bridge Pattern the objects that inherits from the interface will evolve independently and where the client isn t interested in the implementation as he don t have to chose wich is better, rather he want to accomplish one function. Also The main difference is that the Strategy pattern is used when we want to change the algorithm at runtime, and the Bridge pattern is used when we want to change the implementation of an object at runtime. In the Strategy pattern, we encapsulate the algorithm and make it interchangeable, while in the Bridge pattern, we encapsulate the implementation and make it interchangeable.

An example of that is what we had in the exercises where the client only interest is to Hash a document. Here we created a Preview_Hash class and a Full_Hash class. But the Client have only sees and uses hashDocument().  
--> It s a Structural Pattern.