# Lab Report 3

---

## Part 1 - Bugs

```java
@Test  // Test that fails with existing lab3 implementation
public void testReverseEvenNumElements() {
  int[] input = { 1, 2, 3, 4 };
  assertArrayEquals(new int[] { 4, 3, 2, 1 }, ArrayExamples.reversed(input));
}

@Test // Test that passes with existing lab3 implementation
public void testReverseNoElements() {
  int[] input = { };
  assertArrayEquals(new int[] {  }, ArrayExamples.reversed(input));
}
```

![image](https://github.com/AskewParity/cse15l-lab-reports/assets/147351354/9a855c6c-80fc-4e79-9f82-088123fedbda)

The symptom is that the first element of the array is incorrect.

```java
// Buggy Code
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = newArray[arr.length - i - 1];
  }
  return arr;
}

// fixed code
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for (int i = 0; i < arr.length; i += 1) {
    newArray[i] = arr[arr.length - i - 1];
  }
  return newArray;
}
```

There were 2 bugs 
- `newArray` wasn't being changed, instead, garbage/default data was being put into the original `arr`
- the original `arr` is being returned instead of `newArray`

These are solved by
- within the for loop, swapping `arr` and `newArray` so that `newArray` is being filled by `arr` in reverse 
- return `newArray`

---


## Part 2 - Researching Commands
