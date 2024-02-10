![image](https://github.com/derekwu009/cse15l-lab-reports/assets/156358579/0506f82a-7fd5-4857-8123-7e7e59a045c9)# Part 1
Array Methods from week 4's lab:
* Failure-inducing input:
    * JUnit test:
  ```
  public void testReversed2() {
    int[] input1 = {1, 2, 3};
    assertArrayEquals(new int[]{3, 2, 1}, ArrayExamples.reversed(input1));
  }
  ```
    * Associated Code:
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
* Input that doesn't induce failure:
    * JUnit test
  ```
  public void testReversed() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }
  ```
    * Associated Code:
  ```
    static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
  ```
  * Symptoms: ![Symptoms](symp.png)
  * Bug:
     * Before:
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
   * After:
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```
   * Why this fixes the issue:
      * Initially, a new int array is created with `array.length` elements, all initialized to `0`. Becuase of this,
        the for loop sets each element in `arr` to `0`.
      * To fix this, in the for loop, we made it so it sets each element in the newly craeted `newArray` to the elements
        in `arr` starting from the end.

# Part 2
* Command: `grep`
   * -n
```
$ grep -v ".txt" find-results.txt 
technical/plos/
```
   * -v 
```
$ grep -v "journal" find-results.txt 
technical/plos/
technical/plos/pmed.0010008.txt
technical/plos/pmed.0010010.txt
technical/plos/pmed.0010013.txt
technical/plos/pmed.0010021.txt
technical/plos/pmed.0010022.txt
technical/plos/pmed.0010023.txt
technical/plos/pmed.0010024.txt
technical/plos/pmed.0010025.txt
technical/plos/pmed.0010026.txt
technical/plos/pmed.0010028.txt
technical/plos/pmed.0010029.txt
technical/plos/pmed.0010030.txt
technical/plos/pmed.0010034.txt
technical/plos/pmed.0010036.txt
technical/plos/pmed.0010039.txt
technical/plos/pmed.0010041.txt
technical/plos/pmed.0010042.txt
technical/plos/pmed.0010045.txt
technical/plos/pmed.0010046.txt
technical/plos/pmed.0010047.txt
technical/plos/pmed.0010048.txt
technical/plos/pmed.0010049.txt
technical/plos/pmed.0010050.txt
technical/plos/pmed.0010051.txt
technical/plos/pmed.0010052.txt
technical/plos/pmed.0010056.txt
technical/plos/pmed.0010058.txt
technical/plos/pmed.0010060.txt
technical/plos/pmed.0010061.txt
technical/plos/pmed.0010062.txt
technical/plos/pmed.0010064.txt
technical/plos/pmed.0010066.txt
technical/plos/pmed.0010067.txt
technical/plos/pmed.0010068.txt
technical/plos/pmed.0010069.txt
technical/plos/pmed.0010070.txt
technical/plos/pmed.0010071.txt
technical/plos/pmed.0020002.txt
technical/plos/pmed.0020005.txt
technical/plos/pmed.0020007.txt
technical/plos/pmed.0020009.txt
technical/plos/pmed.0020015.txt
technical/plos/pmed.0020016.txt
technical/plos/pmed.0020017.txt
technical/plos/pmed.0020018.txt
technical/plos/pmed.0020019.txt
technical/plos/pmed.0020020.txt
technical/plos/pmed.0020021.txt
technical/plos/pmed.0020022.txt
technical/plos/pmed.0020023.txt
technical/plos/pmed.0020024.txt
technical/plos/pmed.0020027.txt
technical/plos/pmed.0020028.txt
technical/plos/pmed.0020033.txt
technical/plos/pmed.0020034.txt
technical/plos/pmed.0020035.txt
technical/plos/pmed.0020036.txt
technical/plos/pmed.0020039.txt
technical/plos/pmed.0020040.txt
technical/plos/pmed.0020045.txt
technical/plos/pmed.0020047.txt
technical/plos/pmed.0020048.txt
technical/plos/pmed.0020050.txt
technical/plos/pmed.0020055.txt
technical/plos/pmed.0020059.txt
technical/plos/pmed.0020060.txt
technical/plos/pmed.0020061.txt
technical/plos/pmed.0020062.txt
technical/plos/pmed.0020065.txt
technical/plos/pmed.0020067.txt
technical/plos/pmed.0020068.txt
technical/plos/pmed.0020071.txt
technical/plos/pmed.0020073.txt
technical/plos/pmed.0020074.txt
technical/plos/pmed.0020075.txt
technical/plos/pmed.0020082.txt
technical/plos/pmed.0020085.txt
technical/plos/pmed.0020086.txt
technical/plos/pmed.0020088.txt
technical/plos/pmed.0020090.txt
technical/plos/pmed.0020091.txt
technical/plos/pmed.0020094.txt
technical/plos/pmed.0020098.txt
technical/plos/pmed.0020099.txt
technical/plos/pmed.0020102.txt
technical/plos/pmed.0020103.txt
technical/plos/pmed.0020104.txt
technical/plos/pmed.0020113.txt
technical/plos/pmed.0020114.txt
technical/plos/pmed.0020115.txt
technical/plos/pmed.0020116.txt
technical/plos/pmed.0020117.txt
technical/plos/pmed.0020118.txt
technical/plos/pmed.0020120.txt
technical/plos/pmed.0020123.txt
technical/plos/pmed.0020140.txt
technical/plos/pmed.0020144.txt
technical/plos/pmed.0020145.txt
technical/plos/pmed.0020146.txt
technical/plos/pmed.0020148.txt
technical/plos/pmed.0020149.txt
technical/plos/pmed.0020150.txt
technical/plos/pmed.0020155.txt
technical/plos/pmed.0020157.txt
technical/plos/pmed.0020158.txt
technical/plos/pmed.0020160.txt
technical/plos/pmed.0020161.txt
technical/plos/pmed.0020162.txt
technical/plos/pmed.0020180.txt
technical/plos/pmed.0020181.txt
technical/plos/pmed.0020182.txt
technical/plos/pmed.0020187.txt
technical/plos/pmed.0020189.txt
technical/plos/pmed.0020191.txt
technical/plos/pmed.0020192.txt
technical/plos/pmed.0020194.txt
technical/plos/pmed.0020195.txt
technical/plos/pmed.0020196.txt
technical/plos/pmed.0020197.txt
technical/plos/pmed.0020198.txt
technical/plos/pmed.0020200.txt
technical/plos/pmed.0020201.txt
technical/plos/pmed.0020203.txt
technical/plos/pmed.0020206.txt
technical/plos/pmed.0020208.txt
technical/plos/pmed.0020209.txt
technical/plos/pmed.0020210.txt
technical/plos/pmed.0020212.txt
technical/plos/pmed.0020216.txt
technical/plos/pmed.0020226.txt
technical/plos/pmed.0020231.txt
technical/plos/pmed.0020232.txt
technical/plos/pmed.0020235.txt
technical/plos/pmed.0020236.txt
technical/plos/pmed.0020237.txt
technical/plos/pmed.0020238.txt
technical/plos/pmed.0020239.txt
technical/plos/pmed.0020242.txt
technical/plos/pmed.0020246.txt
technical/plos/pmed.0020247.txt
technical/plos/pmed.0020249.txt
technical/plos/pmed.0020257.txt
technical/plos/pmed.0020258.txt
technical/plos/pmed.0020268.txt
technical/plos/pmed.0020272.txt
technical/plos/pmed.0020273.txt
technical/plos/pmed.0020274.txt
technical/plos/pmed.0020275.txt
technical/plos/pmed.0020278.txt
technical/plos/pmed.0020281.txt
```
