# Simple Factory

We've mentioned over and over again that we should not code to concrete implementations, but rather to interfaces. What does this mean? It means the client code should never depend on a specific implementation but on rather a set of public methods that they can rely on. When your code is written to an implementation, then it will work with any new classes implementing that interface through polymorphism. When we code to a concrete class, we're looking for trouble as that code may have to be changed as new concrete classes are added.

Remember our design strategy : identify the objects that vary and seperate them from what stays the same.

Imagine you are building a software for a Pizza Store that you can use to place orders for pizzas. Right now, your code base looks like this:

    public class PizzaStore {
        public Pizza orderPizza() {
        
        Pizza p = new Pizza();
        
        p.prepare();
        p.bake();
        p.cut();
        return p;
    
    }
    
But you have more than one pizza, so you change your method to this:

    public class PizzaStore {
        public Pizza orderPizza(String type) {

        Pizza p;
        
        if (type.equals('cheese')) {
        p = new CheesePizza();
        }
        
        else {
        p = new VeggiePizza();
        }

        p.prepare();
        p.bake();
        p.cut();
        return p;

}

As we get more types of Pizza, we keep having to go back to this method to update it with the new types. 

In situations like this, the solution is very straightforward. We create a PizzaFactory class with a method createPizza() 
that will take care of instantiating the specific Pizza objects. It will look something like this.
    
    public class PizzaFactory {
        public Pizza getPizza(String type) {
    
    }
    }
    public class PizzaStore {
        PizzaFactory pf = new PizzaFactory();
        
        public Pizza orderPizza(String type) {
            Pizza p = pf.getPizza(type);
            return p;
        }
    }
    
Using this approach, we are able to encapsulate the instantiation of the concrete classes into its seperate section. The order pizza method does not need to know anything about the various types of Pizza there are!
It seems like we're simply transferring code to another section but we're forgetting that the Pizza Factory class can have several clients. Any time anywhere else we need to instantiate Pizzas, we can rely on this one specific class.

This is not the Factory design pattern but rather a strategy for encapsulating instantiation.

# Factory Method Design Pattern

The Factory Method Design Pattern defines an interface for creating an object, but lets subclasses decide which classes to instantiate. Factory Method lets a class defer instantiation to subclasses. Similar to simple factory, this design pattern gives us a way to encapsulate the instantiations of concrete types. 

# Example

As your pizza store expands, you realize that different branches of your franchise across the country might offer different types of pizza. The pizzas offered in the New York branch are not the same as the pizzas offered in the San Francisco branch. But you only have one factory class right now. Well, with the factory method pattern, you might not need a concrete factory class at all. We will use subclasses instead. How so?

So, we know that there's a PizzaStore class with a orderPizza method. If we made our PizzaStore an abstract class that subclasses can extend on, we can actually solve our problem.

    public abstract class PizzaStore {
    public Pizza orderPizza(String type); {
            Pizza p = getPizza(type); // the subclasses will depen
            p.bake();
            p.box();
            return p;
        }
        
        public abstract Pizza getPizza(String type) {
            /// abstract method, subclasses will extend.
        }
    }
    
    public class SanFranciscoPizzaStore extends PizzaStore {
        public Pizza getPizza(String type) {
        if (type == "cheese") {
            return new SanFranciscoCheesePizza();
        }
        }
    }
    
    public class NewYorkPizzaStore extends PizzaStore {
        public Pizza getPizza(String type){ 
        if (type == "cheese") {
            return new NewYorkCheesePizza();
        }
        }
    }
    public abstract class Pizza {
        String dough;
        ArrayList<String>toppings = new ArrayList<String>;
    
    }
    
    public class SanFranciscoCheesePizza extends Pizza {
    
        }
    
Now, in the client section, our code would like this:

    public static void main() {
        PizzaStore ps = new SanFranciscoPizzaStore();
        ps.orderPizza("Cheese");
    }
    
Using subclasses, we were able to encapsulate the instantiation of concrete Pizza and as we add new locations, all we have to do is create subclasses for those new locations and add the getPizza method in that. 
Closed for modification. Open for extension.


# Abstract Factory Pattern

The abstract factory pattern is another design pattern that uses factories for encapsulating the instantiation of concrete classes. It does that by providing an interface for creating families of related or dependent objects without specifying their concrete classes.

# Example

You notice that different locations use different ingredients for the same type of pizza. How do you handle this scenario? You create an ingredient factory ofcourse. But unlike the previous example where we used subclasses, we are going to use an interface this time.

    public interface IngredientFactory {
        public Dough createDough();
        public Sauce createSauce();
        public Cheese createCheese();
        public Veggies[] createVeggies();
        
    }
    
    public class NYPizzaIngredientFacotry implements PizzaIngredientFactory() {
        public Dough createDough()  {
            return new ThinkCrustDough();
        }
        
        public Sauce createSauce() {
            return new MarinaraSauce();
        }
        
        public cheese createCheese(){
            return new ReggianoCheese();
        }
    }
    
Now we will have our Pizza classes have an attribute for an ingredient Factory.
   
    public abstract class Pizza {
        String dough;
        ArrayList<String>toppings = new ArrayList<String>;

        }

    public class CheesePizza extends Pizza {
        IngredientFactory if;
        
        public CheesePizza(IngredientFactory if) {
        
        }
    
    }
    
Now, our pizza stores, we make sure they are using the correct ingredients.

    public class SanFranciscoPizzaStore extends PizzaStore {
        public Pizza getPizza(String type) {
            IngredientFactory if = new SanFranciscoIngredientFactory();
            
            if (type == "cheese") {
                return new CheesePizza(if); // a cheese pizza built with custom ingredients from the custom ingredients factory.
            }
        }
    }

    







