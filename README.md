# Oracle certified professional exam preparation

Collections -
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
3. 

Functional interfaces and lambdas -
1. Lambda expression can use local variable if that variable is final or effictively final.

Java OOA, Inner and final classes -

![image](https://user-images.githubusercontent.com/38427828/178449064-df758591-62f9-4b8f-9f4a-aee3e704b930.png)
1. Here we can call new TestOuter.TestInner() which creates us an instance of TestInner object;
2. An instance of the nested class can be created from a class of package mypack using: new TestInner()

Exception handling
1. The rule for overriding a method is opposite to the rule for constructors. An overriding method cannot throw a superclass exception, while a constructor of a subclass cannot throw subclass exception (Assuming that the same exception or its super class is not present in the subclass constructor's throws clause)

Java I/O -
1. FileWriter("text.txt") will throw exception, if text.txt does not exist in filesystem.

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
