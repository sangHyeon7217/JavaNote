## 5. Interface (인터페이스) 🌐

- 추상 클래스보다 **추상화 정도가 높은 클래스**  
- **구현된 것이 전혀 없는 기본 설계도** 📝  
- `class` 대신 `interface`를 사용한다는 점을 제외하고는 클래스 작성과 동일  

### ✅ 장점
- **개발 시간 단축**  
- **표준화 가능** ✅  
- **서로 관계 없는 클래스들에게 관계를 맺어줄 수 있음** 🔗  
- **독립적인 프로그래밍 가능**


# 프로그래밍 인터페이스: 정적 메서드 vs 디폴트 메서드

## 정적 메서드 (`static` method)
### 특징
- `static` 키워드가 붙어진 메서드
- **객체 생성 없이** `인터페이스.메서드명()` 으로 호출
- **인터페이스를 구현한 클래스가 수정 할 수 없음**

### 예제
```java
interface Calculator {
    static int add(int a, int b) {
        return a + b;
    }
}

public class StaticMethodExample {
    public static void main(String[] args) {
        int sum = Calculator.add(10, 20);
        System.out.println("10 + 20 = " + sum);
    }
}
```

### 주요 특징 정렬
| 특징 | 설명 |
|------|------|
| `static` 키워드 | 클래스 또는 인터페이스에 직접 속하는 메서드 |
| 객체 생성 | ❌ 필요 없음 |
| 업로라이드 | ❌ 부가능 |
| 사용 명 | 유틸리티 함수 (ex: `Math.random()`, `Arrays.sort()`) |

---

## 디폴트 메서드 (`default` method)
### 특징
- `default` 키워드가 붙어진 **인터페이스 메서드**
- **인터페이스를 구현한 클래스에서 선택적으로 업로라이드**
- **기본 구현이 제공되며, 기존 인터페이스를 변경 없이 새 기능 추가**

### 예제
```java
interface Calculator {
    default void showInfo() {
        System.out.println("이것은 기본 제공되는 메서드입니다.");
    }
}

class MyCalculator implements Calculator {
    @Override
    public void showInfo() {
        System.out.println("MyCalculator의 새로운 구현!");
    }
}

public class DefaultMethodExample {
    public static void main(String[] args) {
        MyCalculator myCal = new MyCalculator();
        myCal.showInfo();
    }
}
```

### 주요 특징 정렬
| 특징 | 설명 |
|------|------|
| `default` 키워드 | 인터페이스에서 만 사용 가능 |
| 객체 생성 | ✅ 필요 (구현한 클래스의 객체로 호출) |
| 업로라이드 | ✅ 가능 |
| 사용 명 | 인터페이스에 기능 추가 |

---

## 정적 메서드 vs 디포트 메서드 비교
| 비교 항목 | **정적 메서드 (`static`)** | **디폴트 메서드 (`default`)** |
|-----------|-------------------|-----------------|
| 사용 위치 | 인터페이스, 클래스 | 인터페이스 |
| 호출 방법 | `인터페이스.메서드()` | 객체를 통해 호출 |
| 업로라이드 | ❌ 부가능 | ✅ 가능 |
| 명적 | 유틸리티 함수 제공 | 인터페이스에 기본 구현 추가 |

---

## 결론
- `static` 메서드: **객체 없이 조회, 유틸리티 기능**
- `default` 메서드: **기본 구현 제공, 클래스 업로라이드 가능**
- **Java 8 부터 추가되어, 기존 인터페이스를 변경 없이 새 기능을 추가할 수 있다.** 🚀

