# extends와 implement의 차이
상속에 대해서 알아보기 전에, 객체 지향 프로그래밍 (Object-Oriented Programming)에 대해서 간단히 정리해보도록 하겠습니다.
### OPP의 특징
<ul>
  <li> 상속과 인터페이스 </li>
  <li> 다형성, 사용편의성 </li>
  <li> 캡슐화, 정보은닉 </li>
  <li> 자료 추상화 </li>
  <li> 동적 바인딩 </li>
</ul>

## extends?
부모에서 선언/정의한 메소드와 변수를 자식에서 오버라이딩 할 필요 없이 직접 사용할 수 있습니다.
```
class Vehicle {
  protected int speed = 3;
  
  public int getSpeed() {
    return speed;
  }
  public void setSpeed(int speed) {
    this.speed = speed;
  }
}

class Car extends Vehicle {
  public void printspd() {
    System.out.println(speed);
  }
}

public class ExtendsSample {
  public static main(String[] args) {
    car A = new Car();
    System.out.println(A.getSpeed());
    A.printspd();
  }
}
```
car 클래스는 vehicle을 상속받았기 때문에 ExtendsSample 클래스에서 car 참조변수를 통해 부모인 Vehicle의 메소드를 호출하여 사용할 수 있습니다.
Java는 다중상속을 지원하지 않는 대신에, implements(interface)를 사용할 수 있습니다.

## implements?
부모에서 선언한 메소드를 자식에서 재정의(오버라이딩)하여 사용할 수 있습니다.
```
interface TestInterface {
  public static int num = 8;
  public void fun1();
  public void fun2();
}

class InterfaceExam implements TestInterface {
  @Overrice
  public void fun1() {
    System.out.println(num);
  }
  
  @Override
  public void fun2() {
  
  }
}

public class InterfaceSample {
  public static main(String[] args) {
    InterfaceExam exam = new InterfaceExam();
    exam.fun1();
  }
}
```
implements는 반드시 부모의 메소드를 재정의(오버라이딩)하여 사용해야 합니다. <br />

또한 implements는 다중상속을 대신하여 사용할 수도 있습니다.
```
public class Son implements Father, Mother{...}
```

