# Command Design Pattern

This is probably my favorite design pattern so far. The command design pattern encapsulates a request as an object, thereby letting you parameterize other objects with different requests, queue, or log requests, and support undoable operations.

The command Pattern allows you to decouple the requester of an action from the object that actually performs the action. 

Think of a diner. You, the customer, would like to place an order. You say what you would like to order to the waiter. The waiter takes your order and sends it to the kitchen. The kitchen staff look at the order and do the actual cooking. You do not communicate with the kitchen staff directly. You have no idea how they are making what they are making. All you know is that you placed a 'request' with your waiter and your request will be satisifed.

This is the underlying principle of the command design patern. It allows us to seperate the requester of an action from the object that actually performs the action. Let's take a look at a concrete example to see what we really mean.

# Example

Imagine that you are a building the software for a remote control for home automation. There's 8 buttons. 4 On Buttons and 4 Off Buttons. You can control your garage door, your lights in various rooms, your ceiling fan, etc.
Now, so far, this is what you have.

    public class CeilingLight {
        on();
        off();
    }
    
    public class OutdoorLight {
        on();
        off();

    }
    
    public class GardenLight() {
        setDuskTime();
        setDawnTime();
        manualOn();
        manualOff();
    }

You notice that there's a lots of classes with the on and off methods but there's also classes like Garage Door which has methods like doorUp and doorDown. So, the operations we can perform on these vendor classes can vary and not only that but there's going to be more vendor classes in the future with more operations.

This tells us that the individual operations need to be seperated from the remote. The remote should only know how to press buttons and make requests but should not know how the individual requests are being executed.

# Command Pattern to the Rescue

This is where the command design pattern comes into play. The command design pattern tells us to introduce 'command objects' into our design. Different command objects are there for performing different actions. The remote doesn't have to know what the command object will do, all it knows is that it has a bunch of command objects that it can simply call execute on. Think back to our diner example. The command objects are simply the waiter while the customer is the remote. 

Let's see what this pattern will do for our code for the remote control system. We first need to create a command interface.

    public interface Command {
        public void execute();
    }

Now, for any command that the remote will be able to handle such as turning on a light, all we have to do is create a class that implements this interface.

    public class TurnLightOn {
        Light light;
        
        public void execute() {
            light.on();
        }
    
    }
    
    public class TurnLightOff {
        Light light;
        
        public void execute() { 
            light.off();
        }
    
    }
    
    public class OpenGarageDoor {
        GarageDoor gd;
        
        public void execute() {
            gd.goUp();
        }
    
    }

Now, as you might have guessed what we will do with our Remote Class. The remote class will simply have an array of Command objects that we can call execute on. 

    public class RemoteControl {
        ArrayList <Command> OnCommands;
        ArrayList <Command> OffCommands
        
        public void addCommand(Command onCommand, offCommand) {
            OnCommands.add(command);
            OffCommands.add(command)
        }
        
        public void pressOnButtom(int index) {
            OnCommands[index].execute();
        }
        
        public void pressOffButton(int index) {
            OffCommands[index].execute();
        }
    }

With this design strategy, we are able to encapsulate the action from the requester of the action.



