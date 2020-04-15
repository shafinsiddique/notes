# Template Design Pattern

We saw glimpses of the template design pattern when we studied the factory design pattern. The template design pattern is used for solving inheritance issues and provides a solution for code duplication in subclasses. 

The template method pattern defines the skeleton of an algorithm in a method, deferring some steps to subclasses. Template method lets subclasses redefine certain steps of an algorithm without changing the algorithm's interface.

# Example

If we were writing code for preparing coffee and tea, we would notice that the two processes are extremely similar.
For preparing coffee, we need to:
    - boil some water
    - Brew coffee in boiling water
    - pour coffeee in cup
    - Add sugar and milk.

For preparing tea, we need to:
    - boil some water.
    - Steep tea in boiling water.
    - Pour tea in cup.
    - Add Lemon.
    
Currently, our code base looks like this:
    
    public class Coffee {
        void prepareRecipe() {
            boilWater();
            brewCoffeeGrinds();
            pourInCup();
            addSugarAndMilk();
        }
        
        void boilWater() {
            System.out.println("Boiling Water");
        }
        
        void brewCoffeeAndGrinds() {
            System.out.println("dripping Coffee through Filter");
        }
        
        public void pourInCup() {
            System.out.println("pouring into cup");
        }
        
        public void addSugarAndMil() {
            System,out.println("Adding Sugar and Milk");
        }
    }
    
    public class Coffee {
        void prepareRecipe() {
            boilWater();
            SteepTeaBag();
            pourInCup();
            addSugarAndMilk();
            }
    
        void boilWater() {
            System.out.println("Boiling Water");
            }
    
        void SteepTeaBag() {
            System.out.println("Steeping Tea in Bag");
            }
    
        public void pourInCup() {
            System.out.println("pouring into cup");
            }
    
        public void addSugarAndMil() {
            System,out.println("Adding Sugar and Milk");
            }
            }

What we have here is massive code duplication and we can fix this by using inheritance and the template method pattern. We create an abstract class called CaffeineBeverage in which we place the prepareRecipe method. We change the names of the methods SteepTeaBag and BrewCoffeeGrinds into something more general like 'brew.' Then in the coffee and tea classes, we provide an implementation for the brew method.

    abstract class {
        void prepareRecipe(){ 
            boilWater();
            brew();
            pourInCup();
            addSugarAndMilk();

        }
        
        void boilWater() {
            System.out.println("Boiling Water");
        }
        
        public void pourInCup() {
            System.out.println("pouring into cup");
        }
        
        public void addSugarAndMil() {
            System,out.println("Adding Sugar and Milk");
        }

    }

    /// provide implementation for brew in the subclasses.

A template is simply a method that defines an algorithm as a seires of steps. One of more of these steps is defined to be abstract and implemented in a subclas. This ensures the algorithm's structure says unchanged while subclasses provide some part of the implementation.

A hook is a method that is declared in the abstract lcass, but only given an empty or default implementation. This gives subclasses the ability to 'hook into' the algorithm at various points. If they wish, a subclass is also free to ignore the hook.
