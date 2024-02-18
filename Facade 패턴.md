# What

Facade란 건물의 정면을 의미한다. Facade Pattern은 말 그대로 건물의 뒷부분이 어떻게 생겼는지는 보여주지 않고 건물의 정면만 보여주는 패턴이다.  
예를들어 EmployeeFacade 클래스는 메서드의 구현이 어떻게 되어있는지는(건물의 뒷부분) 보여주지 않고  
 어떤 메서드가 있는지(건물의 정면)만 보여준다.   
구체적인 메서드의 구현은 각각 PayCalculator, HourReporter, EmployeeSaver 클래스에 위임하기 때문이다.

출처: [https://inpa.tistory.com/entry/OOP-💠-아주-쉽게-이해하는-SRP-단일-책임-원칙](https://inpa.tistory.com/entry/OOP-%F0%9F%92%A0-%EC%95%84%EC%A3%BC-%EC%89%BD%EA%B2%8C-%EC%9D%B4%ED%95%B4%ED%95%98%EB%8A%94-SRP-%EB%8B%A8%EC%9D%BC-%EC%B1%85%EC%9E%84-%EC%9B%90%EC%B9%99) [Inpa Dev 👨‍💻:티스토리]


# Why


# How