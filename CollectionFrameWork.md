# 📌 Collection Framework

**List**와 **Set**의 특징이 서로 정반대!

- **List**: 순서가 있는 데이터의 집합, **중복 허용**  
  - ex) 웨이팅 명단  
- **Set**: 순서를 유지하지 않는 데이터의 집합, **중복 허용 X**  
  - ex) 여러 색깔의 구슬을 순서 없이 넣고, 순서 없이 뽑기  
- **Map**: 키와 값의 쌍으로 이루어진 데이터의 집합  
  - 순서는 상관없고 **키는 중복 X, 값은 중복 O**  
  - ex) JSON, 우편번호, 지역번호  

## 📌 정렬: `sort()`
- `Collections.sort(List<T>)` → 리스트 정렬  
- `Arrays.sort(T[])` → 배열 정렬  

---

## 📌 Wrapper Class  
기본 자료형을 **객체로 다루기 위해 사용하는 클래스**  

| 기본 타입 | 래퍼 클래스 |
|----------|-----------|
| `byte`   | `Byte`   |
| `short`  | `Short`  |
| `int`    | `Integer` |
| `long`   | `Long`   |
| `float`  | `Float`  |
| `double` | `Double` |
| `char`   | `Character` |
| `boolean`| `Boolean` |

✅ 래퍼 클래스는 모두 `java.lang` 패키지에 포함되어 있어 **import 없이 사용 가능**해!

---

## 📌 파싱(Parsing)
**문자열(String) 등의 데이터를 원하는 형식으로 변환하는 과정**  
- 데이터를 **가공하고 변환하여 원하는 때에 불러올 수 있도록 처리**하는 것  

## 📌 `parseInt()` 메서드란?
**`parseInt()`** 는 **문자열(String)을 정수(int)로 변환하는 메서드**   
`Integer.parseInt(String s)` 를 사용하면 `"123"` → `123` 처럼 **문자열을 정수로 변환**할 수 있다! 🚀  




### ✅ 문자열 → 숫자 변환 (기본 타입)
```java
int num = Integer.parseInt("123");  // "123" → 123
double pi = Double.parseDouble("3.14");  // "3.14" → 3.14
