# 업캐스팅 (Upcasting)과 다운캐스팅 (Downcasting)

업캐스팅(Upcasting)과 다운캐스팅(Downcasting)은 객체 지향 프로그래밍에서 클래스 상속과 다형성을 활용할 때 중요한 개념입니다. 이 두 가지는 객체의 타입을 변환하는 방식에 따라 구분됩니다.

## 1. 업캐스팅 (Upcasting)
업캐스팅은 자식 클래스 객체를 부모 클래스 타입으로 변환하는 과정입니다. 자식 클래스가 부모 클래스를 상속하고 있기 때문에 자식 클래스 객체는 부모 클래스 타입으로 자동으로 변환될 수 있습니다.

### 특징:
- **자동으로 이루어짐**: 자식 클래스 객체는 부모 클래스 타입으로 자동으로 변환됩니다.
- **부모 클래스에서 정의된 메서드만 접근 가능**: 업캐스팅 후 부모 클래스 타입 변수로 참조하기 때문에 부모 클래스에서 정의된 메서드만 사용할 수 있습니다. 자식 클래스에서 새롭게 추가된 메서드는 사용할 수 없습니다.
- **상위 클래스 타입으로 통합 관리**: 여러 자식 클래스를 부모 클래스 타입으로 다룰 수 있기 때문에 코드의 유연성과 확장성이 높아집니다.

### 예시:
```java
class Animal {
    public void sound() {
        System.out.println("Some sound");
    }
}

class Dog extends Animal {
    @Override
    public void sound() {
        System.out.println("Bark");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();  // 자식 클래스 객체 생성
        Animal animal = dog;  // 업캐스팅: 자식 객체를 부모 클래스 타입으로 변환
        animal.sound();  // "Bark" (실제 객체가 Dog이므로 Dog의 sound()가 호출됨)
    }
}

## 2. 다운캐스팅 (Downcasting)

다운캐스팅은 부모 클래스 타입의 객체를 자식 클래스 타입으로 변환하는 과정입니다. 다운캐스팅은 명시적으로 해주어야 하며, 부모 클래스 객체가 실제로 자식 클래스 객체일 때만 가능합니다.

### 특징:
- **명시적으로 작성해야 함**: 다운캐스팅은 자동으로 이루어지지 않으며, 개발자가 명시적으로 `(자식클래스)`와 같은 방식으로 변환을 작성해야 합니다.
- **런타임 시 예외 발생 가능**: 잘못된 다운캐스팅을 시도하면 `ClassCastException`이 발생할 수 있습니다. 즉, 부모 클래스 객체가 실제로 자식 클래스의 객체가 아닌 경우 다운캐스팅을 시도하면 오류가 발생합니다.
- **자식 클래스의 특화된 메서드에 접근 가능**: 다운캐스팅 후에는 자식 클래스에서 추가한 메서드나 속성에 접근할 수 있습니다.

### 예시:
```java
class Animal {
    public void sound() {
        System.out.println("Some sound");
    }
}

class Dog extends Animal {
    public void bark() {
        System.out.println("Bark");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal animal = new Dog();  // 업캐스팅
        animal.sound();  // "Bark"

        // 다운캐스팅: Animal 타입을 다시 Dog 타입으로 변환
        Dog dog = (Dog) animal;  // 명시적인 다운캐스팅
        dog.bark();  // "Bark" (Dog의 특화된 메서드 호출)
    }
}


## 요약

### 업캐스팅 (Upcasting):
- 자식 클래스 객체를 부모 클래스 타입으로 변환
- 자동으로 이루어짐
- 부모 클래스에서 정의된 메서드만 사용 가능
- 코드의 유연성과 재사용성을 높임

### 다운캐스팅 (Downcasting):
- 부모 클래스 타입의 객체를 자식 클래스 타입으로 변환
- 명시적으로 해야 하며, 잘못된 캐스팅 시 예외가 발생할 수 있음
- 자식 클래스의 특화된 메서드와 속성에 접근 가능

업캐스팅은 **자동으로** 이루어지며, 다운캐스팅은 **명시적으로** 수행해야 하므로 이 두 가지는 사용하는 상황과 목적에 따라 다르게 활용됩니다.
