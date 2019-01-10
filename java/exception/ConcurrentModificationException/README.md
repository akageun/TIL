# ConcurrentModificationException 관련

#### 발생 코드
> 리스트 내에 있는 특정 값을 reomve() 할 때 발생.

###### Code
```java
@Test
public void ConcurrentModificationExceptionTestCode() {
    List<Integer> testList = new ArrayList<>(Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8, 9, 10));

    for (Integer integer : testList) {
        if (integer == 3) {
            testList.remove(integer);
        }
    }
}
```

###### 결과
```
java.util.ConcurrentModificationException
	at java.util.ArrayList$Itr.checkForComodification(ArrayList.java:909)
	at java.util.ArrayList$Itr.next(ArrayList.java:859)
	....
```

#### 발생하는 이유
- 멀티 쓰레드에서의 동시성 이슈
- 컬렉션의 불변성

#### 해결법
> Iterator를 사용함.
```java
@Test
public void ConcurrentModificationExceptionTestCode() {
    List<Integer> testList = new ArrayList<>(Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8, 9, 10));

    Iterator<Integer> testIter = testList.iterator();
    while (testIter.hasNext()) {
        Integer val = testIter.next();

        if (val == 3) {
            testIter.remove();
        }
    }
}
```
>JDK 8버전 이상
```java
@Test
public void ConcurrentModificationExceptionTestCode() {
    List<Integer> testList = new ArrayList<>(Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8, 9, 10));

    testList.removeIf(val -> val == 3);
}
```

# 참고링크
https://m.blog.naver.com/PostView.nhn?blogId=tmondev&logNo=220393974518&proxyReferer=https%3A%2F%2Fwww.google.com%2F
https://bestalign.github.io/2015/08/31/top-10-mistakes-java-developers-make-1/
