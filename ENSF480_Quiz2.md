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
