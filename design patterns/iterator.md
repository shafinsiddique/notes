# Iterator Design Pattern

The iterater pattern provides a way to access the elements of an aggregate object sequentially without exposing its underlying representation. 

You can allow client code to glimpse into your data without having them know what data structures you are using. This can be achieved using the iterator pattern.

This allows for simpler client code where the client does not depend on a concrete implementation but rather on a interface.

# Example

Imagine you are building software for a restaurant that is formed by merging two existing restaurants. Your software should allow visitors to view the menu. The menu for this new restaurant is simply a combination of the menus of the two individual restaurants. There's only one problem. The two restaurants are using different data structures to store the contents of their menu. Restaurant A is using an array while Restaurant B is using an ArrayList. You and the other developers are extremely hesitant on changing one of the restaurant codes because there's simply far too much code that relies on that implementation.

This is what the current implementation is:

    public class DinnerMenu {
        MenuItem[] items;
        
        public MenuItem[] getMenuItems(){
            return items;
        
        }
    
    }
    
    public class LunchMenu {
        ArrayList<MenuItems> items;
        
        public ArrayList<MenuItems> getMenuItems {
            return items;
        }
        
    
    }

If you were to build your 'new menu' class from this existing code base, you can imagine what it would look like. Every time you need to go through the items of both menus, you need two seperate loops.

The way to solve this problem is by using an iterator. An iterator will allow the new class to step through the menu items without relying on the data structures.

    public interface Iterator {
        public bool hasNext();
        public MenuItem getNext();
        
        
    }
    
    public class DinnerIterator implements Iterator {
        MenuItem[] items;
        int pos = 0;
        
        // initialize. and implement interface methods.
    
    }
    // do the same for LunchIterator implements Iterator. The attribute will be a Array List instead.

Now, we go into the DinnerMenu and LunchMenu classes and create a "Iterator createIterator()" method in which we simply return a new iterator, which we can call next on and iterate on.

Now, the client code no longer has to worry about which method to call and when. They can be safe knowing that both classes implement iterator and they can just call next on.


