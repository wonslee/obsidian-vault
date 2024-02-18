---
tags:
  - cs/paradigm
aliases:
  - 개방 폐쇄 원칙
  - Open-Closed Principle
---
# What

개방 폐쇄 원칙은 "**확장에는 열려 있어야 하고, 변경에는 닫혀 있어야 한다.**"를 의미한다. 조금 더 쉽게 풀어 쓰자면, **"객체의 기능을 확장할 수 있으면서 기존의 코드(클라이언트 코드)는 수정하지 않는다."** 를 뜻한다.


## 런타임 의존성과 컴파일타임 의존성

OCP는 런타임 의존성과 컴파일타임 의존성에 관한 이야기다.  

![](https://blog.kakaocdn.net/dn/dOQ725/btq2iFlU8jr/J95rLjKVp3gy3UdmkW2Yf1/img.jpg)


Movie는 인터페이스인 DiscountPolicy에 의존하기 때문에, 자식 클래스로 OverlappedDiscountPolicy 클래스를 추가하더라도 기존의 코드(Movie, DiscountPolicy, AmountDiscountPolicy, PercentDiscountPolicy)는 변하지 않는다. 

**새로운 컨텍스트**에 사용되도록 확장할 수 있는 것.  

이 설계는 새로운 할인 정책을 추가해서 기능을 확장하도록 열려있다.  
그리고 기존 코드를 수정할 필요가 없다.  

## [[추상화]]
OCP의 핵심은 **추상화에 의존**하는 것이다.  
OCP에서 '변경에 닫혀 있다'는 것은 구체적으로 말하면 '**추상화 부분은 변경에 대해 닫혀 있다**'라는 뜻이 된다.
그리고 확장에 열려있다는 것은 '구현체 부분은 언제든지 추가하거나 내부 로직을 변경할 수 있다'라는 뜻이 된다.

'폐쇄'를 가능하게 하는 것은 (추상화에 대한) **의존성의 방향**이다.

## OCP vs DIP



# Why

## 높은 응집도와 낮은 결합도

OCP는 높은 응집도와 **낮은 결합도**로 설명이 가능하다. 

객체간의 **결합을 느슨하게 함으로써** 객체들은 한쪽의 변경이 **다른 한 쪽 혹은 다수에 영향을 미치는 것을 방지**할 수 있기 때문에 OCP가 의미 있는 것이다.  


### 높은 [[응집도]]

인터페이스를 상속하는 방식으로 ConnectionMaker을 만들었기 때문에, 
기존의 구현체를 수정한다면 해당 구현체의 전체를 고려해 수정하면 되고 기능이 추가된다면 구현체를 통째로 추가하면 된다는 얘기.

즉 작업의 변경 대상이 명확하다

만약 새로운 구현체 XConnectionMaker을 구현해야 한다고 할 때, 인터페이스를 포함해서 다른 구현체들은 테스트할 필요가 없다. 
이는 ConnectionMaker을 분리하여 응집도를 높인 덕분이다.


### 낮은 [[결합도]]

오브젝트간의 느슨한 연결을 유지하는 것이 바람직하다. 

느슨한 연결 = 관계를 유지하는데 꼭 필요한 최소한만 제공하고, 나머지는 서로 독립적이고 알 필요도 없도록 하는 것

=> 변화에 대응하는 속도가 높아지고 확장 용이


# How
## [[추상화]]

![](https://blog.kakaocdn.net/dn/bCTDnw/btrsfXo3Qrc/1zx0efrVumFhZ72YBeCxZ0/img.png)

Movie는 특정한 할인 정책에 묶이지 않는다.

추상화가 유연한 설계를 가능하게 하는 이유는 **설계가 구체적인 상황에 결합되는 것을 방지**하기 때문이다.

추상화를 이용하면 기존 코드를 수정하지 않고도 기능을 확장할 수 있다. Movie에게 다양한 할인 정책을 적용할 수 있고, 언제든 갈아끼울 수 있다.


## 생성 사용 분리

```java
public class Movie {
    //...
    private DiscountPolicy discountPolicy;

    public Movie(String title, Duration runningTime, Money fee) {
        // ...
        this.discountPolicy = new AmountDiscountPolicy();
    }

    // ...
}
```

위 코드에서는 할인 정책 종류를 추가(기능을 확장)하기 위해 기존의 코드를 수정해야 하기 때문에 OCP를 위반한다.  

또한 하위 클래스를 알고 있기 때문에 결합도가 높아진다.  

유연하고 재사용 가능한 설계를 원한다면 객체에 대한 생성과 사용의 책임을 분리하자.  
가장 보편적인 방법은 객체 생성의 책임을 클라이언트로 옮기는 것이다.  

![](https://img1.daumcdn.net/thumb/R800x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FnXvo2%2FbtrUmg9p6bu%2FcGnyPm3SXk0ryQdHeOiYYK%2Fimg.png)


### FACTORY

FACTORY : 객체에 대한 생성과 사용을 분리하기 위해 객체 생성에 특화된 객체.

![](https://blog.kakaocdn.net/dn/vNtjY/btq6lk1gLVc/R9dHFuQtRqt1fnXBeSlSY1/img.png)

## [[DI]]

생성과 사용의 책임을 분리한 후에 사용되는 방법이 DI이다. 




## 구체적인 예시
### [[JDBC Driver Manager]]



![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fdqs36A%2FbtqZpfr81Sw%2FGK2ht1F6Ch87rK0FIAmIoK%2Fimg.png)

각 DB들과 Driver들은 변경될 수 있고 확장에는 열려있습니다. 반면에 그러한 변경과 확장이 일어나더라도 JDBC Driver Manager가 제공하는 인터페이스만 그대로 사용하면 되기 때문에 Java 애플리케이션(클라이언트 코드)에는 영향을 미치지 않습니다(=**변경이 전파되지 않는다**). 입니다.


### [[OOP#클래스와 추상 데이터 타입 의 차이점]]

