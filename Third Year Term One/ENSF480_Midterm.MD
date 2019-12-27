# ENSF 480 Midterm Review

## Templates in C++

* Template functions are generic functions taht can be instantiated for different signatures.
* Template functions will be defined similar to other functions, proceeding with keyword template following with the parameter list.
* The parameter type may have one or more types.

* Each formal parameter must be preceded by the keyword "class" or "typename"
* forward declaration (which is basically a function prototype), the parameter names don't need to be the same.

* A template function can be declared extern, inline or static

* Forward declaration can be used with extern, where you have template <class T> and extern T min(T,T);
* Template functions can also be overloaded as long as the signature of each instance is distinguished by the argument type or number

### Template Function Specialization

Sometimes there are cases that the general template expansion is inappropriate or inefficient for a particular type. Using Template Function Specialization, you can combat this issue.

## Template Classes

### Template class forward declarations
Template class forward declarations are done the same as template function declarations.

### Template Class Specialization
Template class specializations are similar to template function specialization, except now with template <>

### Iterators
* An iterator is an object that provides a general method of successively accessing each element of a container type. It's an object that enables a programmer to traverse linear containers like arrays, vectors & listsl.

```c
    template <class T> class Array;

    template <class T>
    class Array {
        T* storage;
        int size;
    public:
        class ArrayIterator {
            friend class Array<T>;
            Array<T>* ptr;
            int index;
        public:
            ArrayIterator(Array<T>& ar): ptr(&ar), index(0) {}
            T operator++;
            T operator--;
        };

        Array(int s): size(s) {
            storage = new T[size];
        }

        T& operator [] (int i) {
            return storage[i];
        }
    };

    template <class T>
    T Array<T>::ArrayIterator::operator++() {
        index++;
        if(index >= ptr->size)
            index = 0;
        return ptr->storage[index];
    }

    T Array<T>::ArrayIterator:operator++(int) {
        T temp = ptr->storage[index];
        index++;
        if(index > ptr->size) {
            index = 0;
        }
        return temp;
    }

```

## Inheritance

* Inheritance is a relationship among classes where a subclass inherits the structure and behaviour of the superclass
* Defines the "is a" or generalization/specialization hierarchy
* structure: instance variables / Behaviour: instance methods

### Base Class Design

* Protected members are inherited but not public members
* Member functions whose implementations depends on details of derivations should be virtual functions.

```c
    class Person {
        public: 
            Person();
            virtual ~Person();
            virtual display();

        protected:
            int age;
            char *name;
    };
```

#### Scope Resolution Operator
The scope resolution operator is basically Base Class::method

* Usually the scope resolution operator is unnecessary. The only cases when this may be necessary when the inherited member's name is reused in the derived class
* when two or more classes define an inherited member with the same name

* When initializing the constructors of a derived class, you call the base class as well as all inherited classes

### Virtual functions
* A virtual function is a special function invoked through a public base class reference/pointer, and is bound dynamically
* THe instance invoked is determined by the class type of the actual object
* Resolution of a virtual function is transparent
* There is either virtual or pure virtual

### Virtual destructors
* A destructor should be usually declared virtual if it is responsible for removing allocated memory
* Reminds the inheriting classes to redefine this function and do their own cleanup

### Order of construction
The base class constructors are called in the order in which they appear in the class derivation list.

### Derived class copy constructor

If a dervied class explicitly defines its own copy contructor, the definition completely overrides the default definition and is responsible for copying its base class component. 

```c
    class Base {...};

    class Derived: public Base {
        public:
            Derived(const Derived& x): Base(x) {}
    }
```

### Derived class Assignment Operator

If a derived class explicitly defines its own assignment operator, the definition completely overrides the default definition and is responsible for copying its base class component

```c
    Derived& Derived::operator = (const Derived* rhs) {
        Base::operator = (rhs);
        return *this;
    }
```

### Derived class destructor

Derived class destructor is never responsible for destroying the members of the base object. The compiler will always implicitly invoke the destructor of the base part.

### Realization

The realization relationship is the relationship between two model elements. Where one model element realizes the behaviour of the other element specifies.

### Friend Functions

The following components of a program can be friends to a class:

* A global function
* A member function of other classes
* Another class

An example of a friend class

```c
    class List;
    class Node {
        private:
            int data;
            Node* next;
            friend class List;
        public:
            Node(int a) {data=a};
            int get_dat() {return data;}
    };

    class List {
        ...
    };
```

Friend Member functions

```c
    class C {
        friend void B::f();
        int c;
        public:
            C();
            void print();
    }
```

### Operator Overloading

* A class designer can provide a set of operators to work with objects of the class
* This can be achieved by defining an operator function
* It need not be a member function, but must take at least one class argument. This prevents the programmer from overloading the behaviour of operators for built-in data types.

#### Member or non-member?
* If the first parameter of an overloaded function must be an object of another class, the function must be a nonmember
* The assignment "=", "[]", and "()" "->" must be a class member

#### Type conversion
* Constructors with only one argument act as a implicit type conversion operator to convert the given argument to the type of class

##### Explicit Type Conversion

Explicit type casting can occur:

```c
    String::operator char* () {
        return storageM;
    }

    String s("ABCD");
    char* st = (char*)s;
```