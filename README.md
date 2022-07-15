# Oracle certified professional exam preparation personal notes
- Author: Rakhimjonov Shokhsulton
## Collections
- Adding into list should be sequential. IndexOutOfBoundException occurs while trying to add element one step ahead size of list
- ```Object.clone()``` clones array, but objects will point to same object. For example **array1 == array2** *false*, **array1[0] == array2[0]** *true*
###### Immutable collections
- Immutable collections does not support any changes after creation. UnsoppertedException will be thrown while trying of editing it.
- ```List.of()``` and ```List.copyOf()``` creates immutable collections.
- Immutable collections will throw NullPointerException in case creating copy of Collection with null object contains in it.

###### Deque extends of Que
- First in first out.
- Methods - ```push(E e), pollFirst(), poll(), pollLast()```

###### Collection interfaces
- Comparator used to sort method of Arrays - ```Arrays.sort``` has one functional method ```compare(T t, T t)``` returns **int**

## Java data types 
- Operator == goes first, and then = 
- ```isBlank()``` returns true if the string is empty or contains only white space codepoints, otherwise false. 
isEmpty returns true if, and only if, ```length()``` is 0
- final variable must initialize while constructor is only one or in static init or itself respectively

## Controlling program flow - if,else,switch
###### General
- Switch can work with ```int short byte char String```

## Functional interfaces and lambdas
- Lambda expression can use local variable if that variable is final or effictively final.

## Java OOA, Inner and final classes
###### General
- Garbage collector collects only instance of class, not static variables.
- When a programmer does not define **ANY** constructor, the compiler inserts one automatically, the access modifier of which is same as that of the class.
###### Real life scenario
![image](https://user-images.githubusercontent.com/38427828/178449064-df758591-62f9-4b8f-9f4a-aee3e704b930.png)
> Here we can call new TestOuter.TestInner() which creates us an instance of TestInner object;
> An instance of the nested class can be created from a class of package mypack using: new TestInner()


## Java OOP
- Encapsulation must provide private (in case of immutablity should be final) fields and public accessors in several scenarious. 
Exception handling
- The rule for overriding a method is opposite to the rule for constructors. An overriding method cannot throw a superclass exception, while a constructor of a subclass cannot throw subclass exception (Assuming that the same exception or its super class is not present in the subclass constructor's throws clause)
- Sublcass extended from its superclass must fullfil defualt contructor if superclass doesn't provide custom constructor, or its custom constructor

## Java I/O
- ```FileWriter("text.txt")``` will throw exception, if text.txt does not exist in filesystem.
- ```Files.line(Path p)``` also ```Files.line(Path p, Charset c)``` returns **Stream of Strings**
- ```Files.readAllLines(Paths.get(INPUT_FILE))``` returns **List of Strings**

## Optionals 
- ofNullable() returns empty Optional
- orElse() is null safe
- orElseGet() throws NullpointerException if value is not present and other is null
- Optional.of method throws NullPointerException if you try to create an Optional with a null value

## Exception handling
###### General
- Checked exception must be handled before run. Such as ```Exception``` and it subclasses. Uncheked exeptions could be unhandled and can be thrown wile runtime. Such as ```RuntimeException``` or ```Error```

## Concurrency
###### General
- CyclicBarrier allows multiple threads to run independently but wait at one point until all of the coordinating threads arrive at that point. Once all the threads arrive at that point, all the threads can then proceed. It is like multiple cyclists taking different routes to reach a particular junction. They may arrive at different times but they will wait there until everyone arrives. Once everyone is there, they can go on futher independent of each other.
###### Synchronization and ReentrantLock
- A thread exclusively owns the intrinsic lock between the time it has acquired the lock and released the lock.
- When method or variable is synchronized, thread can acquire a lock on the class
###### Deadlock, livelock and starvations
- Deadlock is - Thread 1 and 2 are said to be deadlocked when Thread 1 is blocked waiting for Thread 2 to release a resource, while Thread 2 is blocked waiting for Thread 1 to release another resource.
- Livelock is - when threads become so busy in responding to each other that they are unable to perform any real work.
- Starvation is - when thread waiting too long while threadpool start it

## Java streams
###### General
- For Java streams needs ```source``` and ```terminal operation```. Also exist short circuit methods. We will discus it down below
###### Source

###### Short circuit
- groupingBy method returns Map<Object, Object>
- collect(Collectors.**joining**) will return String, which combine each String element of Iterable
###### Terminal operations 
- Terminal operations returns void and next methods called after will provide compilation error

## Modules
- jmod tool to create JMOD files and list the content of existing JMOD files. functions -> create|extract|list|describe|hash
- jdeps --list-deps moduleA.jar -> it will list all the modules on which moduleA depends. It will show an error if moduleA requires any other application module. 

## Java functional interfaces and its methods
- BiConsumer<T, U> - accept(T t, U u)
- BiFunction<T, U, R> - R apply(T t, U u)
- BinaryOperator<T> - extends from BiFunction<T, T, T>. Itself has 2 static methods, minBy, maxBy using Comparator<T> and result BinaryOperator<T>
- BiPredicate<T, U> - boolean test(T t, U u)
- BooleanSupplier - boolean getAsBoolean()
- Consumer<T> - accept(T t)
- DoubleBinaryOperator - double applyAsDouble(double left, double right)
- DoubleConsumer - accept(double t)
- DoubleFunction<T> - T apply(double t)
- DoublePredicate - boolean test(double t)
- DoubleSupplier - boolean get()
- DoubleToIntFunction - int applyAsInt(double t)
- DoubleToLongFunction - long applyAsLong(double t)
