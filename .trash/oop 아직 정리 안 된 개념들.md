
## 아직 정리 안 된 개념들

- **Overriding**
    
    > 조상 클래스 및 인스턴스로부터 **상속받은** **메서드**의 내용을 **변경**하는 것
    
    당연히 조상 클래스에 정의되어있는 그대로 써도 상관 없다. 그러면 애초에 자손쪽에서 따로 정의하지 않아도 쓸 수 있다.
    
    그러나 자손 클래스 자신에 맞게 변경해야 하는 경우엔 오버라이딩이 필요하다. 2D 좌표를 3D 좌표로 옮겼을때의 getLocation 함수를 상상해보자.
    
    > 오버라이딩의 **조건** : 메서드의 **선언부**가 **조상의 것과 완전히 일치**해야 한다. 즉, 이름, 매개변수, 반환 타입이 똑같아야 한다.
    
    > **접근 제어자**는 조상의 것보다 좁은 범위로 변경할 수 없다. 조상의 것이 protected라면, 이를 오버라이딩하는 자손의 method는 (default)나 private이 될 수 없다. protected, public만 가능.
    
    > 더 많은 예외를 선언할 수 없다.
    
- super과 this
    
    > super : **조상클래스로부터 상속받은 멤버를 참조**하는데 사용되는 참조변수.
    
    멤버변수와 메서드 지역변수의 이름이 같을 때 this를 붙여서 구별했듯이, 상속받은 멤버와 해당 클래스에서 정의된 멤버 이름이 같을 때 super로 구별할 수 있다.
    
    조상의 멤버와 자신의 멤버를 구별한다는 점을 제외하면, super과 this는 **근본적으로 같다**. 모든 인스턴스 메서드에는 자신이 속한 **인스턴스의 주소가 지역변수로 저장**되는데, 이것이 **참조변수**인 this와 super의 값이 된다.
    
    > super() : **조상 클래스의 생성자를 호출**
    
    Object 클래스를 제외한 모든 클래스의 생성자는 첫 줄에 반드시 자신의 다른 생성자 또는 조상의 생성자를 호출해야 한다. 아니면 컴파일러가 자동적으로 `super();` 을 첫줄에 추가한다.
    
- `**@Override**` 와 오버라이딩
    
    실수를 방지할 목적으로 자바에서는 `@Override` 어노테이션을 지원
    
    super class의 메서드를 오버라이딩할 때 사용
    
    일괄적으로 개발자 스스로가 Override 되는 모든 매서드에 대해서 바로 이 @Override를 붙여 놓는 것입니다. 이것은 분명히 명확하고 옳바른 습관입니다.
    
- **다형성**(polymorphism)
    
    > 여러가지 형태를 가질 수 있는 능력. 조상 클래스 타입의 참조 변수로 자손 클래스의 인스턴스를 참조할 수 있도록 한다.
    
    ```java
    public static Map<Long, Member> my_map = new HashMap<>();
    ```
    
- **generics**
    
- 단일 상속
    
    > 자바는 단일 상속만을 허용한다. 그래서 하나 이상의 클래스로부터 상속을 받을 수 없다.
    
    ```java
    class TVRadio extends TV, Radio // Error!
    ```
    
- **Object** 객체
    
    > 모든 클래스 상속계층도의 최상위에 있는 조상클래스
    
    ![https://www.javatpoint.com/images/core/objectclass.gif](https://www.javatpoint.com/images/core/objectclass.gif)
    
    ```java
    class Tv { 
    	// empty
    }
    ```
    
    컴파일러는 위의 코드를 읽고 **자동적으로** `**Object` 클래스로부터 상속**받도록 한다.
    
    ```java
    class Tv extends Object { 
    	// empty
    }
    ```
    
    그래서, 아무런 변수나 메서드를 선언하지 않은 경우에도 Object의 기본적인 public 메서드를 사용할 수 있는것이다.
    
    ```java
    Tv.toString()
    Tv.equals()
    Tv.hashCode()
    ```
    
