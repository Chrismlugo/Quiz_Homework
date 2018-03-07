Quiz Homework

###1.What does the word 'polymorphism' mean?

The word polymorphism is a greek word. "poly" meaning many and "Morph" meaning change.
Polymorphism in programming really means that one object can assume many forms.

###2.What does it mean when we apply polymorphism to OO design? Give a simple Java example.

In OO design polymorphism is where we treat one instance of a class the same as another.

for example a Room class can be a Bedroom and also a meetingroom as they are subclass types of a Room superclass.

# here is an example in java. this class Clown is a subclass of a Person superclass
public class Clown extends Person {


    public Clown(String name) {
        super(name);
    }
##  The method here passes in an Person instance
    public String throwsPie(Person person){              
        return getName() + " throws pie at " + person.getName() + "...Splat!";
    }
}
## Here in the test, when we can see that we can pass in a clown instance and the Person class will take the role of a Clown.
@Test
   public void canThrowPieAtClown() {
       Clown clown2 = new Clown("Rollo");
       assertEquals("Bobo throws pie at Rollo...Splat!", clown.throwsPie(clown2));

   }

###3.What can we use to implement polymorphism in Java?

We can use an abstract Classes which would be the superclass of classes that we want to take the form.

We can also use interfaces which a class can implement and become a type of that interface.

###4.How many 'forms' can an object take when using polymorphism?

many. in the case of using an abstract class, the superclass can have as many concrete classes inherit from it but there can only be one superclass

For interfaces, you can have as many interfaces as you could need and multiple classes can implement them.

###5.Give an example of when you could use polymorphism.

If for example I was designing a game where I had multiple character types e.g. knights, pirates, wizards; you could say that all of these characters are different types of a character class.
Here I would use an abstract class CHARACTER which would take in all attributes and methods common to all character types, such as name and health. I could then create new classes for each character type which would extend from the CHARACTER class.
I can then write methods which can pass in an instance of the superclass, and I can call that method again but can pass in any class which extends from CHARACTER and the superclass instance will take the form of that subclass.


###6.What do we mean by 'composition' in reference to object-oriented programming?

Composition is where a class is made using other class objects.


###7.When would you use composition? Provide a simple example in Java.
You would use composition to get the functionality needed for an object to behave the way we want it to.

# here we can see a stereo is composed of a recordDeck, cdPlayer and radio object.
    public Stereo(String name, RecordDeck recordDeck, CdPlayer cdPlayer, Radio radio) {
        this.name = name;
        this.currentVolume = 0;
        this.maxVolume = 10;
        this.recordDeck = recordDeck;
        this.cdPlayer = cdPlayer;
        this.radio = radio;
    }
  }
# the objects the class is composed of allow the stereo to use that objects methods.
  public String tuneRadio(String station){
        return "Radio: " + radio.tune(station);
    }

    public String playCd(String title){
        return cdPlayer.play(title);
    }

    public String playRecord(String title){
        return recordDeck.play(title);
    }

###8.What is/are the advantage(s) of using composition?

The key advantage of composition is it allows us to use all the functionality of the object/objects that the class is being composed of. It helps us avoid overriden methods and re-use code we need.


###9.What happens to the behaviours when the object composed of them is destroyed?

If an object is composed of other objects/behaviours, when it is destroyed all the objects it was composed of are also destroyed.
