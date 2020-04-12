# Facade Design Pattern

The facade design pattern literally puts on a 'facade' for your code so that clients have an easier time using it.
The facade pattern provides a unified interface to a set of interfaces in a subsystem. Facade defines a higher level interfact that makes the subsystem easier to use. The easiest way to understand the facade pattern is by seeing it in example, so let's dive right into that.

# Example

Let's say you are building a system to automate your home theater. You essentially want to be able to write code such that when it executes you are able to watch a movie. This is currently what you have to do to play a movie.
    
    public static void main() {
        popper.on();
        popper.pop();
        lights.dim(10);
        screen.down();
        projector.on();
        projector.setInput(dvd);
        projector.wideScreenMode();
        
        amp.on();
        amp.setDvd(dvd);
        amp.setSurroundSound();
        amp.setVolume();
        dvd.on();
        dvd.play(movie);

    }
    
You realize that if you ship your code like this, your clients are gonna have an extremely hard time setting up the movie. There's just simply too much for them to do, and they might have no reason worrying about this kind of complexity.

We can easily resolve this issue by building a facade class that does all of these tasks for us without the clients having to worry about individual components.

    public class HomeTheaterFacade {
        Amplifier amp;
        Popper p;
        Lights l;
        Dvd d;
    
        public HomeTheaterFacade(Amplifier a, Popper p, Lights l, DVD d)'
        
        public void playMovie(Movie m) {
        `p.on();
        `p.pop();
        l.dim(10);
        s.down();
        projector.on();
        projector.setInput(dvd);
        
        /// basocally just do everything here.
        }
    }
    
Now, in your client code:

    public static void main() {
        HomeTheaterFacade ht = new HomeTheaterFacade(amp, light, l, d);
        ht.playMovie("Frozen");
    }
    

    


