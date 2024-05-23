# Part 1:
1. A failure-inducing input:
```
 @Test
    public void shouldFail(){
    int[] check = {1,0,1,0};
    int[] test = {0,1,0,1};
    ArrayExamples.reverseInPlace(test);
    assertArrayEquals(check,test);
    }
```
2. No failure:
```
@Test
    public void shouldPass(){
    int[] check = {0,0,0,0};
    int[] test = {0,0,0,0};
    ArrayExamples.reverseInPlace(test);
    assertArrayEquals(check,test);
    }
```


