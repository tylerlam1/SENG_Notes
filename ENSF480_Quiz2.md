# ENSF 480 Quiz II Notes
## Decorator Pattern

* The intent of the decorator pattern is to attach additional responsiblities to an object dynamically. Decorators provide flexible alternative to subclassing to extend flexibility.

* Motivation - You want to add properties to an existing object.
* Sometimes, a large number of independent extensions are difficult and would produce an explosion of subclasses to support every combination.

* The extsnion from FileInputStream -> BufferedInputStream is also an example of the usage of the decorator pattern.

The decorator is a structural pattern.

### Example

Let's say you have a visual component Widget. This will be your interface. It has the function display.

You need to define an abstract decorator for this. This abstract decorator aggregates the widget, and also implements Widget.

You also need a concrete decorator, that extends Decorator. This can modify the thickness, and display. It can also modify the scrollbar type.

Here are the steps:

1. Definition of the component

```Java
    public interface Widget {
        void display();
    }
```

2. Define an abstract decorator

```Java
    abstract class Decorator implements Widget {
        Widget widget;
        public Decorator(Widget w) {
            widget = w;
        }
    }
```
3. Define a concrete decorator

``` Java
    public class Border extends Decorator {
        private int thickness;

        public Border(Widget w, int thick) {
            super(w);
            thickness = thick;
        }

        @Override;
        public void display() {
            widget.display();
            System.out.println("It's border thickness is: " + thickness);
        }
    }
```

4. More decorators

```Java
    public class Scrollbar extends Decorator {
        private String type;

        public Scrollbar(Widget w, String st) {
            super(w);
            type = st;
        }

        @Override
        public void display() {
            widget.display();
            System.out.println("It's scrollbar type is.: " + type);
        }
    }
```

5. Creating one or more concrete components

```Java
    class Text implements Widget {
        protected int length;
        String text;
        public Text(String s) {
            text = s;
            length = text.length();
        }

        public void display() {
            System.out.println("This is a plain text: " + text + "and its length is: " + length);
        }
    }
```

6. More components

```Java
    class WrappedText extends Text {
        private int width, lines;
        public WrappedText(String s, int w, int h) {
            super(s);
            width = w;
            lines = length / width;
        }

        public void display() {
            System.out.println("This is a wrapped Text: " + text + "and it's length is" + length + " and width is " + width);
        }
    }
```

* THe decorator pattern provides flexible alternative to subclassing for extending functionality
* Allows behaviour modification at runtime rather than compilation time
* Difficulty of wide variety of permutation can be solved, and you can wrap a component with any number of decorators
* Supports reusability and maintainability

## Singleton Pattern

* User shouldn't be allowed to create instances of the singleton object
* Need to have a private class-data-field of the Singleton
* Need to have a public class method to have access to private class data field

Steps to develop a Singleton Class:

1. Create a Singleton class

```Java
    public class Singleton {
        private static Singleton onlyInstance;
        private ArrayList<String> usernameList;
        private ArrayList<String> passwordList;
        private ArrayList<String> nameList;

        private Singleton() {
            usernameList = new ArrayList<String>();
            passwordList = new ArrayList<String>();
            nameList = new ArrayList<String>();
        }

        public static Singleton getOnlyInstance() {
            if(onlyInstance == null)
                onlyInstance = new Singleton();
            return onlyInstance;
        }

        public static void setOnlyInstance(Singleton onlyInstance) {
            SingletonLogin.onlyInstance = onlyInstance;
        }

        public void addUsername(String username) {
            usernameList.add(username);
        }

        public void setUsername(int index, String newUsername) {
            usernameList.set(index, newUsername);
        }
    }
```

* Singleton is a famous pattern as its known to be the simplest to learn.
* It is useful for using a single copy of a shared resource.
* However, Singleton classes cannot be subclassed.

## Observer Pattern

Observer pattern uses the MVC idea.

* Model = Classes in your system that are related to the internal representation of the state of the system
* View = Classes in your system that display the state of the model to the user
* Controller = classes that connect the model and view

* Observer = an object that "watches" the state of anither object and takes action when the state changes in some way
* Observable object = An object that allows observers to examine it

Steps:
1. Create an observer interface with a n update method
2. Create either an interface or abstract class for subject that contains methods to add or remove an observer object
3. Create a class that implements subject
4. Create one or more class that implements observer:

1. Create an Observer Interface:

```Java
    public interface Observer {
        public void update(double data);
    }
```

2. Create an interface of Subject

```Java
    interface Subject {
        public void register(Observer o);
        public void remove(Observer o);
        public void notifyObserver();
    }
```

3. Implementation of class implementing  Subject

```Java
    class Weather implements Subject {
        private double temp;
        private ArrayList<Observer> observers;

        public Weather(double t) {
            observers = new ArrayList<Observer>();
            temp = t;
        }

        public void register(Observer o) {
            observers.add(o);
            o.update(temp);
        }

        public void remove(Observer o) {
            ...
        }

        public void notifyObserver() {
            for(int i = 0; i < observers.size(); i++) {
                Observer o = observers.get(i);
                o.update(temp);
            }
        }

        public double getTemp() {
            return temp;
        }

        public void setTemp(double t) {
            temp = t;
            notifyObserver();
        }
    }
```

4. Implement classes that use Observer

```Java
    class HorizontalDisplay implements Observer {
        double temp;
        Subject weather;

        public HorizontalDisplay(Subject w) {
            weather = w;
            weather.register(this);
        }

        @Override
        public void update(double temp) {
            this.temp =  temp;
            display();
        }

        public void display() {
            // code to display horizontally
        }
    }
```

* Supports loose coupling between objects that interact with each other
* Allows sending data to other objects without any change to the Subject or Observer classes
* Dynamic relationship between subject and observer: Relationship can be established at runtime