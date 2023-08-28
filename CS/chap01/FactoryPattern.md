# 팩토리 패턴
- 객체 생성 부분을 떼어내 추상화한 패턴
- 상속 관계에 있는 두 클래스
    - 상위 클래스 : 중요한 뼈대를 결정
    - 하위 클래스 : 객체 생성에 관한 구체적인 내용을 결정
- 상위 클래스와 하위 클래스가 분리됨 -> 느슨해짐
    - 상위 클래스 : 인스턴스 생성 방식에 대해 전혀 알 필요가 없기 때문에 더 많은 유연성을 갖게 됩니다.
    - 객체 생성 로직 : 코드를 리팩토링 -> 한 곳만 고칠 수 있게 되니 유지 보수성 ↑

## 예시
레시피가 따로 있는 바리스타 공장
- 레시피 : 하위 클래스
- 바리스타 공장 : 상위 클래스
- 팩토리 패턴 : 생산 공정

```java
abstract class Coffee{ 
    public abstract int getPrice();
    
    @Override
    public static toString () {
        return "Hi this coffee is " + this.getPrice();
    }
}

class CoffeeFactory{
    public static Coffee getCoffee(String type, int price){
        if ("Latte".equalsIgnoreCase(type)) return new Latte(price);
        else if ("Americano".equalsIgnoreCase(type)) return new Americano(price);
        else {
            return new DefaultCoffee();
        }
    }
    
    
}
class DefaultCoffee extends Coffee{
    private int price;
    
    public DefaultCoffee(){
        this.price = -1;
    }
    
    @Override
    public int getPrice(){
        return this.price;
    }
}
class Latte extends Coffee{
  private int price;

  public DefaultCoffee(){
    this.price = -1;
  }

  @Override
  public int getPrice(){
    return this.price;
  }
}
class Americano extends Coffee{
  private int price;

  public DefaultCoffee(){
    this.price = -1;
  }

  @Override
  public int getPrice(){
    return this.price;
  }
} 
public class HelloWorld{
  public static void main(String[] args) {
    Coffee latte = CoffeeFactory.getCoffee("Latte", 4000);
    Coffee ame = CoffeeFactory.getCoffee("Americano", 3000);
    System.out.println("Factory latte ::"+ latte);
    System.out.println("Factory ame ::"+ ame);
  }
}
// 결과
// Fatory latte ::Hi this coffee is 4000
// Fatory ame ::Hi this coffee is 3000
```

#### 코드를 살펴보면 if문으로 문자열 비교 기반으로 로직이 구성 되어있는데
#### Enum 또는 Map을 이용하는 방법도 있다.

- Enum : 상수의 집합을 정의할 때 사용되는 타입
  - 상수나 메소드 등을 집어넣어서 관리 
  - 코드 리팩토링이 편해진다 => 해당 집합에 관한 로직 리팩토링 시 이 부분만 수정하면 됨 