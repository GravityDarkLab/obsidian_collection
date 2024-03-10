It is a [[Testing patterns]].

`Assume there is no getter for the private field “key” of the Authentication class but we need to access it for our test`.

Reflection testing pattern is a technique used to test internal implementation details of a class, such as private methods, fields and constructors. This technique is used in cases where the internals of a class need to be tested, and is used in unit testing.

A good example of using reflection in Java is testing a private method that calculates the result of an operation and checking if the result is correct.

## Code example:
```java
import java.lang.reflect.InvocationTargetException;
import java.lang.reflect.Method;

public class ReflectionTest {
  private int sum(int a, int b) {
    return a + b;
  }

  public void runTest() throws NoSuchMethodException, InvocationTargetException, IllegalAccessException {
    Class<ReflectionTest> clazz = ReflectionTest.class;
    Method sumMethod = clazz.getDeclaredMethod("sum", int.class, int.class);
    sumMethod.setAccessible(true);
    int result = (int) sumMethod.invoke(this, 1, 2);
    assert result == 3;
  }
}
```
In the above example, the private method `sum` is being tested using reflection by getting a reference to the method using `clazz.getDeclaredMethod` and then invoking it using `sumMethod.invoke`. The `setAccessible` method is used to set the accessibility of the private method so that it can be invoked.
![[Bildschirm­foto 2023-01-31 um 14.56.46.png]]

## Problems
- Can obscure what is going on in code.
- Maintenance of reflection code is difficult.
- Performance can be slow 


``` 
→ Use reflection sparingly.
→ Usually the need to use reflection is a sign for bad design.
→ Refactor after writing the test.
```

