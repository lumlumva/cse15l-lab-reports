# Lab Report 3

**Part 1**

The method with bug I chose from `ArrayExamples.java`
```
public class ArrayExamples {

// Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
}
```

* A failure-inducing input for the buggy program, as a JUnit test and any associated code
```
public class ArrayTests {
	@Test
  public void testReversed() {
    int[] input1 = {1, 2, 3, 4, 5};
    int[] expectedOutput1 = {5, 4, 3, 2, 1};
    int[] actualOutput1 = ArrayExamples.reversed(input1);
    assertArrayEquals(expectedOutput1, actualOutput1);
```

* An input that doesn't induce a failure, as a JUnit test and any associated code
```
public class ArrayTests {
	@Test
  public void testReversed() {
    int[] input2 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input2));
```

