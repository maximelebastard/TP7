TP 7
===

Question 2
---

### Q 2.1

** 1 **
The RetryRunner class inherits from the **BlockJUnit4ClassRunner**, which is a JUnit class. RetryRunner is a class used to run test. Its behavior is to retry tests until the number of retries reaches the MAX_ATTEMPTS value.
Retrying the tests allows to detect if the failure is due to a random event.

**2**
RetryRunner is tested by the **RetryRunnerTest** test case. The RetryRunnerTest has a method that always throws a MathIllegalStateException and another that sometimes MathIllegalStateException, depending on a random.
The second method will return before the end of all the retries, and test if the retries allows to detect a random bug.

**3**
The **Well512a** test is based on known sequences of number. By injecting a known seed, the test can predict which random numbers will be generated, and check if they are the predicted ones. An error will be thrown if the generation differs from the expected generation.
On the other hand, the **RandomDataGeneratorTest** does not assumes that it knows which numbers will be generated, and assumes that it is fully random. This test just generates a big amount of numbers and checks some criterias about them like the bounds, the uniqueness between two generations and the behavior with negatives ranges.

**4**
The **TestUtils** class defines a few new assertions:
* *Assertions with delta*: An assertion that allows a certain amount of errors between expected value and actual value
* *Assertions with Complex numbers*: This assertion manipulates Complex objects to compare their Real and Imaginary values
* *Assertions with double array*: Compares two Double arrays and expects them to have the same elements
* *Serialized objects check*: Checks that the serialization result of two serializable objects are the same.
* *Matrices check*: verifies that two matrices are close or same

**5**
The **Prime** exception are tested giving a few negative numbers and checking if they throw an exception.
We could generate random negative numbers and assert them to throw an exception ; and retry it a thousand times.

### Q 2.2

**6**
These tests are testing the BOBYQAOptimizer, which is an implementation of complex maths computing optimization. It tests given values, and expects the same results than the precalculated ones.