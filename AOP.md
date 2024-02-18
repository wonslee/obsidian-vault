---
tags:
  - cs/programming-model
---

# What
= 관점 지향 프로그래밍

 = 애플리케이션에서 여러 곳에서 **자주 반복되는 기능들을 독립적으로 모듈화**하는 프로그래밍 모델.  
 = 횡단 관심사를 `@Aspect` 어노테이션을 통해서 추출하여 특정 메소드가 호출될 때 특정 시점에 동작하도록 할 수 있는 것이다.

기존의 횡단(공통) 관심사를 계속해서 코딩해야 되는 불편함이 사라지고 개발자들은 **핵심 관심사에만 집중**하여 개발을 할 수 있게 되는 것이다. 또한 핵심 관심사에만 집중함으로써 자연스럽게 **SRP**를 준수할 수 있게 된다.

## 예시
### `@Transactional`

비즈니스 로직과 트랜잭션 관리 로직이 혼재해있다면 한 객체에서 여러 책임을 갖게 되는 것이며 코드의 중복이 발생하게 된다. Spring에서는 `@Transactional` 이라는 선언적 트랜잭션 기능을 구현하여 AOP를 적용하도록 한다. 

### `@ControllerAdvice`
 [해외 포스팅](https://reflectoring.io/spring-boot-exception-handling/#controlleradvice)을 보면 실제로 ControllerAdvice가 AOP로 구현되어 있음과 예외 처리를 공통의 부가 기능으로 제공한다는 점에서 AOP의 **Advice**로부터 이름을 따왔음을 알 수 있다. 

출처: [https://mangkyu.tistory.com/246](https://mangkyu.tistory.com/246) [MangKyu's Diary:티스토리]

# Why


# How