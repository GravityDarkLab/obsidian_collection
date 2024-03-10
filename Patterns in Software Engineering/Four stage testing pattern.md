It is a [[Testing patterns]].

![[Bildschirm­foto 2023-01-31 um 15.01.37.png]]

1.  **Setup**: This stage involves setting up the test environment and test data. This may involve creating test objects, initializing variables, or setting up any other preconditions that are necessary for the test to run. It's important to set up the test environment so that it is in a known state before the test begins.
2.  **Exercise**: This stage involves executing the code under test. This may involve invoking a method, setting a property, or executing any other code that is relevant to the test. The goal of this stage is to exercise the code under test to determine how it behaves in a specific scenario.
3.  **Validation**: This stage involves verifying that the code under test behaves as expected. This may involve checking the return value of a method, checking the state of an object, or validating any other output from the code under test. It's important to verify that the code under test behaves as expected so that you can determine whether it is working correctly.
4.  **Teardown**: This stage involves cleaning up the test environment after the test has completed. This may involve releasing any resources that were acquired during the test, resetting any state, or cleaning up any other test artifacts. It's important to clean up the test environment so that it is in a known state for the next test.

## Code example:
```java
import org.junit.After;
import org.junit.Before;
import org.junit.Test;

public class FourStageTestPatternExample {
  private static class Calculator {
    int add(int a, int b) {
      return a + b;
    }
  }

  private Calculator calculator;

  @Before
  public void setUp() {
    calculator = new Calculator();
  }

  @Test
  public void testAddition() {
    // Stage 2: Exercise
    int result = calculator.add(1, 2);

    // Stage 3: Verification
    assert result == 3;
  }

  @After
  public void tearDown() {
    calculator = null;
  }
}
```
![[Bildschirm­foto 2023-01-31 um 15.07.48.png]]
