# Ramda

## 함수형 인터페이스
- 단 하나의 추상 메서드만 선언된 인터페이스
- 함수형 인터페이스 타입의 참조변수로 람다식을 참조할 수 있음
- (단, 함수형 인터페이스의 메서드와 람다식의 매개변수 개수와 반환타입이 일치해야 함.)

## 람다식 예제

```java
int add(int x, int y) {
    return x + y;
}
```

위의 메서드를 람다 표현식을 이용해 아래와 같이 단축할 수 있다.

```java
(int x, int y) -> {
    return x + y;
};
```

매개변수 타입도 생략할 수 있다.

```java
(x, y) -> {
    return x + y;
};
```

함수에 리턴문 한 줄만 있을 경우 더욱 더 단축할 수 있다.

```java
(x, y) -> x + y;
```

## 람다식 변환 예제

### 1. `max` 함수 변환

**기존 코드:**
```java
int max(int a, int b) {
    return a > b ? a : b;
}
```

**람다식 변환:**
```java
(a, b) -> a > b ? a : b;
```

---

### 2. `printVar` 함수 변환

**기존 코드 :**
```java
void printVar(String name, int i) {
    System.out.println(name + "=" + i);
}
```

**람다식 변환:**
```java
(name, i) -> System.out.println(name + "=" + i);
```

---

### 3. `square` 함수 변환

**기존 코드 :**
```java
int square(int x) {
    return x * x;
}
```

**람다식 변환:**
```java
x -> x * x;
```

---

### 4. `roll` 함수 변환

**기존 코드 :**
```java
int roll() {
    return (int) (Math.random() * 6);
}
```

**람다식 변환:**
```java
() -> (int) (Math.random() * 6);
```

