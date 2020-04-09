# Singleton Design Pattern

There are many objects we only need one of: threaded pools, caches, dialog boxes, objects that handle preferences and registry settings, objects used for logging. For a lot of these objects, instantiating more than once can have devastating impacts.

The Singleton Design pattern is a design pattern for solving this problem. By using the Singleton Design Pattern, we can ensure that only ONE instance of a object is created and that no other instances are created anywhere else in the program.

But, how does the Singleton accomplish that? Like, how can it possibly stop us from doing something like this:

    Singleton a = new Singleton();
    Singleton b = new Singleton();

Or doing that a 100 times. After all, the constructors are always public.

Well, not necessarily. The Singleton Design pattern uses private constructors, so no code outside of the class can actually instantiate it.

You might be asking, "well that's great, but what use is a class to us if we can't even instantiate objects." Read what I wrote again, "no code OUTSIDE of the class can actually instantiate." Code inside the class can still instantiate the object and we will be doing that through the use of static methods (methods that we do not need to instantiate an object for).

# Code

    public class Singleton {
        Singleton instance;
        private Singleton() {
        
        }
        
        public Singleton getInstance() {
            if (instance == null) {
                return new Singleton();
            }
            
            return instance;
        }
    }

As you can see, the code is extremely simple. With a few changes, we can ensure that there's only ONE instance of a certain object in the entire program.

# Limitations

If the program is using multi threading and two threads instantiate at the exact same time, we would actually have two instances of the class.

In order to solve this, we need to use the 'synchronized' keyword which ensures that only one thread can access it at the same time.

# Example

The Head First Design Pattern book by O'Reily talks about an example of designing the software for controlling the chocolate boilers of a chocolate factory. The original programmers went through great lengths to ensure that the ChocolateBoiler class which includes methods such as fill(), drain(), boil(), isEmpty(), is being extremely careful. In boil, they check whether the chocolate is already boiled and whether the container is empty. All these checks are there to ensure they don't boil something that's already been boiled.

Now, the programmers that designed this software did not use the Singleton Design pattern so initially, we were able to create as many instances of the ChocolateBoiler class as we want. Now, they do ensure that the class is only instantiated when the chocolate is ready to be boiled. However, what if, we accidentally create two instances or three instances. When it is iniitally instantiated, the class automatically assumes that the chocolate is not boiled. We could end up boiling the same chocolate 3x.

At a time like this, it's really helpful to use the Singleton Design Pattern and ensure that we can't create more than one instance of a class.




