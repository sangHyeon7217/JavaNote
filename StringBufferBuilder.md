# 📌 StringBuffer vs. StringBuilder

## 🔹 StringBuffer
- **Java 1.0에서 도입**.
- **가변(Mutable) 객체**로, 문자열을 수정할 수 있다.
- **스레드 안전(Thread-safe)**하여 멀티스레드 환경에서 안전하게 사용할 수 있지만,  
  성능은 `StringBuilder`보다 느릴 수 있다.

## 🔹 StringBuilder
- **Java 5에서 도입**.
- **가변(Mutable) 객체**로, 문자열을 수정할 수 있다.
- **성능이 뛰어나며**, 문자열을 자주 변경해야 할 때 유용하지만,  
  **스레드 안전하지 않으므로** 멀티스레드 환경에서는 주의가 필요하다.

---

## 🛠 예제 코드

```java
public class StringTest {
    public static void main(String[] args) {
        // StringBuffer (스레드 안전)
        StringBuffer sb1 = new StringBuffer("Hello");
        sb1.append(" World");
        System.out.println(sb1); // Hello World

        // StringBuilder (성능 우수)
        StringBuilder sb2 = new StringBuilder("Hello");
        sb2.append(" World");
        System.out.println(sb2); // Hello World
    }
}

## 🔍 StringBuffer vs. StringBuilder 차이점

| 특징 | StringBuffer | StringBuilder |
|------|-------------|--------------|
| **속도** | 느림 (동기화 처리) | 빠름 (동기화 없음) |
| **멀티스레드 환경**  | 안전함 (Thread-Safe)    | 안전하지 않음 (Thread-Unsafe) |
| **싱글스레드 환경**  | 성능이 상대적으로 낮음    | 성능이 좋음                   |
| **주요 메서드**      | `append()`, `insert()`, `delete()`, `reverse()`       | `append()`, `insert()`, `delete()`, `reverse()` |
