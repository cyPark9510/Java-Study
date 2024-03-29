# 다형성이란?

>객체 지향 프로그래밍에서 하나의 타입이 여러 가지 형태로 변환될 수 있는 것을 말한다.
이를 통해 한 객체가 여러 타입의 기능을 제공할 수 있고,
유사한 객체들을 일관성 있게 다룰 수 있어서 코드의 가독성과 유지 보수성을 향상시킬 수 있다.

- 다형성은 타입 상속을 통해 구현된다.
- 즉, 하위 타입은 상위 타입이 될 수 있다.

위 코드는 Animal 클래스를 상속받는 다양한 동물 클래스를 정의하고, 다형성을 이용해 sound 메서드를 호출하는 예시이다.
각각 다른 형태의 동물 객체이지만, 모두 Animal 타입으로 변환될 수 있어서 이들을 일관성 있게 사용할 수 있다.

# 추상화란?

>데이터나 프로세스 등 의미가 비슷한 개념이나 의미 있는 표현으로 정의하는 과정을 의미한다.

## 추상화 방법
추상화는 ***특정한 성질***을 뽑아내는 것과 ***공통된 성질을 일반화하는 것***으로 나눌 수 있다.

### 특정한 성질

>특정 객체나 개념에서 중요한 속성이나 기능을 추출해 내는 것을 의미한다.
이를 통해 해당 객체나 개념을 더 간결하고 명확하게 표현할 수 있다.

- 사용자에서 아이디, 이름을 뽑아내서 USER 테이블로 추상화할 수 있다.
- 통화와 금액을 통해 Money 클래스로 추상화할 수 있다.

### 공통된 성질(일반화)

>여러 개체들이 공통으로 가지는 특징을 추상화하여 하나의 개념으로 일반화하는 것을 의미한다.
이러한 추상화를 통해 개념을 단순화하고 구조화하여 다양한 구현체를 대표할 수 있는 상위 타입을 도출할 수 있다.
이 상위 타입은 여러 구현체를 대표하는 역할을 하며, 인터페이스로 많이 표현된다.

- LG 프린터, 삼성 프린터를 프린터로 추상화할 수 있다.
- 지포스, 라데온을 GPU로 추상화할 수 있다.

## 추상화와 다형성

- 추상화는 다형성과 관련이 있다.
- 추상화는 복잡한 시스템에서 필요한 부분만 추려내어 단순화하는 과정이다.
- 추상화 타입은 여러 구현을 추상화할 때 사용된다.
- 추상화 타입은 공통된 속성을 표현하며, 여러 구현 클래스를 대표하는 상위 타입을 도출할 수 있다.
- 추상화 타입은 인터페이스로 많이 표현된다.
- 추상화 타입과 구현은 클래스를 상속으로 연결하며, 구현은 추상화 타입이 제공하는 기능의 구현을 담당한다.
    + 구현을 담당하는 클래스를 콘크리트(concrete) 클래스라고 한다.
- 추상화 타입은 구현을 감추므로 기능의 구현이 아닌 의도를 더 잘 드러낼 수 있다.

## 추상화 시점

- 새로운 추상 타입이 생기면 프로그램의 복잡도는 증가한다.
    + 따라서 아직 존재하지 않는 기능에 대한 이른 추상화는 주의해야 한다.

- 추상화를 하는 시점은 실제 변경이나 확장이 발생할 때 필요한 시점이다.
    + 추상화를 잘하면 변경에 유연해지기 때문에 코드 유지보수성이 향상된다.

## 추상화 이점

- 클라이언트 코드 수정 없이, 기능을 수정할 수 있는 변경의 ***유연함***을 얻을 수 있다.
- 모듈별 기능을 한곳에 모을 수 있다.
    - 이것이 바로 OCP

# OCP(Open-Closed Principle)

>확장에는 열려있어야 하고, 변경에는 닫혀있어야 한다.
> 
> - 기능을 변경하거나 확장할 수 있다.
> - 기능을 사용하는 코드는 수정하지 않아야 한다.

#### OCP는 변경이나 확장에 대한 비용을 낮춰준다. 