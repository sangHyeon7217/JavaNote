# **HashSet과 HashMap 인터페이스 설명**


## ✅ **HashSet이란?**
`HashSet`은 **Set 인터페이스**를 구현한 클래스이며, **중복을 허용하지 않는 자료구조**입니다.  
내부적으로 **HashMap을 사용하여 데이터를 저장**하고, **순서를 보장하지 않습니다**.

### ✅ **HashSet의 주요 특징**
| 특징 | 설명 |
|------|------|
| **중복 허용 X** | 같은 값을 여러 번 저장할 수 없음 |
| **순서 보장 X** | 입력한 순서대로 저장되지 않음 |
| **빠른 검색** | 내부적으로 `HashMap`을 사용하여 `O(1)`에 가깝게 빠른 검색 |
| **null 값 허용** | `null` 값을 한 개만 저장 가능 |

### ✅ **HashSet 사용 예제**
```java
import java.util.HashSet;
import java.util.Set;

public class HashSetExample {
    public static void main(String[] args) {
        Set<String> set = new HashSet<>();
        
        // 값 추가
        set.add("Java");
        set.add("Python");
        set.add("C++");
        set.add("Java"); // 중복 값 (저장되지 않음)

        // 출력
        System.out.println(set); // [Java, C++, Python] (순서는 다를 수 있음)

        // 값 포함 여부 확인
        System.out.println(set.contains("Java")); // true

        // 값 제거
        set.remove("Python");

        // 크기 확인
        System.out.println(set.size()); // 2

        // 모든 값 제거
        set.clear();
        System.out.println(set.isEmpty()); // true
    }
}

```


##  HashMap이란?
`HashMap`은 **Map 인터페이스**를 구현한 자료구조이며, **키(key)와 값(value)의 쌍**으로 데이터를 저장합니다.  
내부적으로 **해시 테이블(Hash Table)**을 사용하여 **빠르게 데이터를 저장하고 검색할 수 있습니다**.

##  HashMap의 주요 특징
| 특징 | 설명 |
|------|------|
| **Key-Value 구조** | 하나의 키(key)에 하나의 값(value)을 저장 |
| **중복된 키 X** | 같은 키가 추가되면 기존 값이 덮어쓰기 됨 |
| **순서 보장 X** | 입력한 순서대로 저장되지 않음 |
| **빠른 검색** | `O(1)`에 가까운 속도로 데이터 검색 가능 |
| **Key에 null 허용** | `null` 키 1개만 허용, 값에는 여러 개 허용 가능 |

##  HashMap 사용 예제
```java
import java.util.HashMap;
import java.util.Map;

public class HashMapExample {
    public static void main(String[] args) {
        Map<Integer, String> map = new HashMap<>();

        // 값 추가
        map.put(1, "Apple");
        map.put(2, "Banana");
        map.put(3, "Cherry");
        map.put(2, "Orange"); // 기존 값(2, "Banana")이 덮어쓰기 됨

        // 출력
        System.out.println(map); // {1=Apple, 2=Orange, 3=Cherry}

        // 특정 키의 값 가져오기
        System.out.println(map.get(2)); // Orange

        // 키 존재 여부 확인
        System.out.println(map.containsKey(3)); // true

        // 값 존재 여부 확인
        System.out.println(map.containsValue("Banana")); // false

        // 키 제거
        map.remove(1);

        // 크기 확인
        System.out.println(map.size()); // 2

        // 모든 값 제거
        map.clear();
        System.out.println(map.isEmpty()); // true
    }
}
```

##  HashMap 내부 구조
`HashMap`은 **배열 + 연결 리스트(또는 트리) 구조**로 되어 있습니다.  
해시 충돌이 발생하면, 동일한 해시 값의 데이터들이 **체이닝(Chaining) 방식**으로 연결 리스트에 저장됩니다.

```java
static class Node<K,V> {
    final int hash;
    final K key;
    V value;
    Node<K,V> next;
}
```

- `put(key, value)` → 해시 함수로 해시 값 생성 후, **배열의 해당 위치에 저장**.
- 해시 충돌이 많아지면 **연결 리스트 → 트리(Tree) 구조로 변경**하여 성능 최적화.

##  언제 HashMap을 사용할까?
| 사용 목적 | 적합한 컬렉션 |
|-----------|-------------|
| **키-값 구조로 데이터 저장** | `HashMap` |
| **특정 키를 기반으로 값 저장 및 조회** | `HashMap` |
| **빠른 검색** | `HashMap` |

##  결론
- **`HashMap`**: 키-값 쌍 저장 (빠른 검색 가능).
- **순서를 보장하지 않으며, 빠른 데이터 조회와 검색이 가능**.





