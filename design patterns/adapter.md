# Adapter Design Pattern

The adapter design pattern in object oriented programming does exactly what an adaptor does in the real world. If you have ever travelled with electronics, you might have noticed that the pins on your charger might not fit into the sockets. In order to make it fit, we use an adapter. We plug our charger into the adapter and then the adapter fits into the wall. Adapters in object oriented programming are similar in the sense that they convert the interface of a class into another interface.

The adapter pattern converts the interface of a class into another interface the clients expect. Adapter lets classes work together that couldn't otherwise because of incompatible intefaces.

# Simple Example

Imagine you have a duck interface and some classes implementing that duck interface for a video game you are making.

    public interface Duck {
        public void quack();
        public void fly();
    }
    
    public class MallardDuck implements Duck {
        public void quack() {
            // implementation
    }
        public void fly() {
            // implementation
    }
    }

Now, imagine you also have a turkey interface.

    public interface Turkey {
        public void fly();
        public void gobble();
    
    }   
If you were running short on ducks and had to use turkey, with your current implementation, you wouldn't be able to. Turkeys dont quack, they gobble. What you need is an adapter class.

    public class TurkeyAdapter implements Duck {
        Turkey turkey;
        
        public void quack() {
            turkey.gobble();
        }
        
        public void fly() {
            turkey.fly();
        }
    }
    
# Real World Example

In earlier versions of Java, the early collection types (Vector, Stack, Hashtable) implemented a method called elements(), which returns an Enumeration object. The enumeration interface allows you to step through the elements without knowing the specifics of how they are managed in the collection.

When Sun released their more recent Collections classes, they began using an Iterator interface that does the exact same thing as Enumeration but also allows you to remove items from Collections.

This resulted in the Enumerator interface being exposed when we only want the Iterator interface. For that, we need an adapter.

Similar to our simple example, we need an adapter class that implements the target interfae (Iterator) and is composed with an instance of the adaptee class (Enumerator).


