# **Lab Report 2**

## ***Part One***

## ***Part Two***
This part would analyze a bug in method `reversed()` in `ArrayExamples.java` and implement tests to show this in `ArrayTests.java`. \
The code before change:
```
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = newArray[arr.length - i - 1];
  }
  return arr;
}
```
1. Failure-inducing input:
```
int[] input2 = {10, 20, 30};
assertArrayEquals(new int[] {30, 20, 10}, ArrayExamples.reversed(input2));
```
* Create a new nonempty integer array `{10, 20, 30}` in `ArrayTests.java` and expected to return `{30, 20, 10}`. 
2. Input that does not induce a failure:
```
int[] input1 = { };
assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
```
* Since this input is empty, and the original code only sets the size of the result array (0 in this case), the returned array is null, which passes the test accidentally.
3. Symptom:
* As is shown below, for array input `{10, 20, 30}`, the terminal returns a failure message.
* The returned value for the first element is expected to be `30` but actually `0`.
* The terminal does not report a problem in the test case of the empty array, so the empty input passes the test. \
(screenshot here)
4. Bug:
* This failure is caused by a lack of code to copy data from the original array to the new one.
* To fix this, write a for loop to deep copy the elements to the new array, which has to be written before the reverse.
* After the copy, the original array can reverse its elements by copying the elements in the new array in a reverse order. \
**Note: To fix this problem, must do deep copy rather than shallow copy (i.e write `int[] newArray = arr;` instead of the for loop).**

The code before change:
```
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = newArray[arr.length - i - 1];
  }
  return arr;
}
```
The code after change:
```
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for (int j = 0; j < arr.length; j++) {
    newArray[j] = arr[j];
  }
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = newArray[arr.length - i - 1];
  }
  return arr;
}
```

## ***Part Three***
