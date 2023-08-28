# 프로그래밍 패러다임
프로그래머에게 프로그래밍의 관점을 갖게 해주는 역할을 하는 개발 방법론
<br>ex) 객체지향 프로그래밍(프로그램을 상호 작용하는 객체들의 집합) vs 함수형 프로그래밍(상태 값을 지니지 않는 함수 값들의 연속)

- 프로그래밍 패러다임
  - 선언형 : 무엇을 풀어내는가에 집중하는 패러다임
    - 함수형 : 순수 함수들을 블록처럼 로직 구현, 고차 함수를 통해 재사용성을 높임
  - 명령형
    - 객체지향 : 객체들의 상호 작용을 표현, 데이터를 객체로 취급함 -> 처리 속도 느림
      - 추상화 : 복잡한시스템으로부터 핵심적인 개념 또는 기능을 간추려내는 것
      - 캡슐화 : 객체의 속성과 메소드를 하나로 묶고 일부를 외부에 감추어 은닉
      - 상속성 : 상위 클래스의 특성을 하위 클래스가 이어받아서 재사용하거나 추가 및 확장
      - 다형성 : 하나의 메소드나 클래스가 다양한 방법으로 동작하는 것
      - 오버로딩 : 같은 이름을 가진 메소드를 여러 개 두는 것 
      - 오버라이딩 : 상위 클래스로부터 상속받은 메소드를 하위 클래스가 재정의하는 것
      - 설계 원칙(SOLID)
        - 단일 책임 원칙 : 모든 클래스는 각각 하나의 책임만 가져야 한다
        - 개방-폐쇄 원칙 : 유지 보수 사항이 생긴다면 코드를 쉽게 확장할 수 있도록 하고 수정할 때는 닫혀 있어야 한다.
        - 리스코프 치환 원칙 : 프로그램의 객체는 프로그램의 정확성을 깨뜨리지 않으면서 하위 타입의 인스턴스로 바꿀 수 있어야 한다
        - 의존 역전 원칙 : 자신보다 변하기 쉬운 것에 의존하던 것을 추상화된 인터페이스나 상위 클래스를 두어 변하기 쉬운 것에 변화에 영향 받지 않게 한다.
    - 절차형 : 로직이 수행되어야 할 연속적인 계산 과정으로 이루어져 있다