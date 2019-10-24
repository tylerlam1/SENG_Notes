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