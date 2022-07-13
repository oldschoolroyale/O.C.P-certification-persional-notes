# Oracle certified professional exam preparation personal notes

Collections -
1. adding into list should be sequential. IndexOutOfBoundException occurs while trying to add element one step ahead size of list
[Immutable collections]
1. Immutable collections does not support any changes after creation. UnsoppertedException will be thrown while trying of editing it.
2. List.of() and List.copyOf() creates immutable collections.
3. Immutable collections will throw NullPointerException in case creating copy of Collection with null object contains in it.

[Deque extends of Que]
1. First in first out.
2 Methods - push(E e), pollFirst(), poll(), pollLast()

Java data types - 
1. operator == goes first, and then = 
2. isBlank() returns true if the string is empty or contains only white space codepoints, otherwise false. 
isEmpty returns true if, and only if, length() is 0
3. final variable must initialize while constructor is only one or in static init or itself respectively

Functional interfaces and lambdas -
1. Lambda expression can use local variable if that variable is final or effictively final.

Java OOA, Inner and final classes -

![image](https://user-images.githubusercontent.com/38427828/178449064-df758591-62f9-4b8f-9f4a-aee3e704b930.png)
1. Here we can call new TestOuter.TestInner() which creates us an instance of TestInner object;
2. An instance of the nested class can be created from a class of package mypack using: new TestInner()

Java OOP -
1. Encapsulation must provide private (in case of immutablity should be final) fields and public accessors in several scenarious. 
Exception handling
2. The rule for overriding a method is opposite to the rule for constructors. An overriding method cannot throw a superclass exception, while a constructor of a subclass cannot throw subclass exception (Assuming that the same exception or its super class is not present in the subclass constructor's throws clause)
3. Sublcass extended from its superclass must fullfil defualt contructor if superclass doesn't provide custom constructor, or its custom constructor

Java I/O -
1. FileWriter("text.txt") will throw exception, if text.txt does not exist in filesystem.
2. Files.line(Path p) also Files.line(Path p, Charset c) returns Stream<String>
3. Files.readAllLines(Paths.get(INPUT_FILE)) returns List<String>

Optionals - 
1. ofNullable() returns empty Optional
2. orElse() is null safe
3. orElseGet() throws NullpointerException if value is not present and other is null
4. Optional.of method throws NullPointerException if you try to create an Optional with a null value

Concurrency -
1. CyclicBarrier allows multiple threads to run independently but wait at one point until all of the coordinating threads arrive at that point. Once all the threads arrive at that point, all the threads can then proceed. It is like multiple cyclists taking different routes to reach a particular junction. They may arrive at different times but they will wait there until everyone arrives. Once everyone is there, they can go on futher independent of each other.
2. Deadlock is - Thread 1 and 2 are said to be deadlocked when Thread 1 is blocked waiting for Thread 2 to release a resource, while Thread 2 is blocked waiting for Thread 1 to release another resource.
3. Livelock is - when threads become so busy in responding to each other that they are unable to perform any real work.
4. Starvation is - when thread waiting too long while threadpool start it

Java streams -
1. groupingBy method returns Map<Object, Object>
2. 

Modules -
1. jmod tool to create JMOD files and list the content of existing JMOD files. functions -> create|extract|list|describe|hash
2. jdeps --list-deps moduleA.jar -> it will list all the modules on which moduleA depends. It will show an error if moduleA requires any other application module.
3. 

Java functional interfaces and its methods -
1. BiConsumer<T, U> - accept(T t, U u)
2. BiFunction<T, U, R> - R apply(T t, U u)
3. BinaryOperator<T> - extends from BiFunction<T, T, T>. Itself has 2 static methods, minBy, maxBy using Comparator<T> and result BinaryOperator<T>
4. BiPredicate<T, U> - boolean test(T t, U u)
5. BooleanSupplier - boolean getAsBoolean()
6. Consumer<T> - accept(T t)
7. DoubleBinaryOperator - double applyAsDouble(double left, double right)
8. DoubleConsumer - accept(double t)
9. DoubleFunction<T> - T apply(double t)
10. DoublePredicate - boolean test(double t)
11. DoubleSupplier - boolean get()
12. DoubleToIntFunction - int applyAsInt(double t)
13. DoubleToLongFunction - long applyAsLong(double t)
