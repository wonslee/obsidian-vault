---
tags:
  - cs/programming-language
---


# What

## [[OOP]] [[프로그래밍 언어]]

## [[JVM]]

## [[C++]] vs Java

https://theheydaze.tistory.com/598

## 변수

### [[Wrapper]]
 
### [[call by value]] vs [[call by reference]]


Java에서 인자로 넘길 때는 **주소값이란 값을 복사**하여 넘기는 것이므로 **call by value**라고 할 수 있다. **원시 타입뿐만 아니라 참조 타입까지 모두 적용**된다.

따라서 원본 객체의 프로퍼티까지는 접근이 가능하나, **원본 객체 자체를 변경할 수는 없다**.



C/C++와 같이 변수의 주소값 자체를 가져올 방법이 없으며, 이를 넘길 수 있는 방법 또한 있지 않다.
[[포인터]]가 없기 때문이다.


```java
User a = new User("gyoogle");   // 1

foo(a);

public void foo(User b){        // 2
    b = new User("jongnan");    // 3
}

```

1 : a에 User 객체 생성 및 할당(새로 생성된 객체의 주소값을 가지고 있음)
 a   -> User Object [name = "gyoogle"]
 
2 : b라는 파라미터에 a가 가진 주소값을 복사하여 가짐. 즉 b == a

 a   -> User Object [name = "gyoogle"]
               ↑     
 b   --------------
 
3 : 새로운 객체를 생성하고 새로 생성된 주소값을 b가 가지며 a는 그대로 원본 객체를 가리킴
 
 a   -> User Object [name = "gyoogle"]
                   
 b   -> User Object [name = "jongnan"]



## [[불변성]]

final.


## [[캐스팅]]

## Stream API

# Why

## [[OOP]]



# How


## [[Java 예외 처리]]
