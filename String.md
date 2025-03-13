# String Class

## Java String Concatenation: 연결 연산자

```java
String firstName = "John";
String lastName = "Doe";
System.out.println(firstName + " " + lastName);
```

## String Special Characters

문자열은 반드시 큰따옴표(`" "`) 안에 작성해야 합니다. 그렇지 않으면 Java가 문자열을 제대로 해석하지 못하고 오류를 발생시킵니다.

```java
String txt = "We are the so-called "Vikings" from the north."; // 오류 발생
```

### 해결 방법
**이스케이프 문자(`\"`)를 사용하여 큰따옴표를 문자열 안에서 정상적으로 표시**

```java
String txt = "We are the so-called \"Vikings\" from the north.";
```

### Escape Characters
| Escape character | Result | Description |
|-----------------|--------|-------------|
| `\'` | `'` | Single quote |
| `\"` | `"` | Double quote |
| `\\` | `\` | Backslash |

## 🔥 Immutable (불변성)
`String` 인스턴스의 내용은 바꿀 수 없다.

```java
String str1 = "대한";
String str2 = "민국";
String str3 = str1 + str2;
// str1의 값과 str2의 값을 합치더라도 str1에 값이 합쳐지는 것이 아니라 str3 변수의 새로운 주소지가 생긴다!!
```

```java
String str1 = new String("abc");
String str2 = new String("abc");
System.out.println("str1==str2의 결과: "+ (str1==str2));// false

// 이유: new String()을 사용하면 Heap 메모리에 새로운 객체가 생성됨. 즉, 주소지가 다름

String str3 = "abc";
String str4 = "abc";
System.out.println("str3 == str4의 결과: " + (str3 == str4)); // true
// 이유: 문자열 리터럴("abc")을 String Pool이라는 공유 메모리 영역에 저장함
```

```java
String str1 = new String("abc");
String str2 = new String("abc");
System.out.println("str1=" + str1); // abc
System.out.println("str1.toString()=" + str1.toString()); // toString 한 것과 같다

System.out.println("str1==str2의 결과: " + (str1 == str2)); 
// 객체가 instance화 되어 heap 영역으로 서로 다른 주소지가 생성되어 false
System.out.println("str1.equals(str2)의 결과: " + (str1.equals(str2))); // true

// 모양(값) 비교는 .equals()
// Object 객체의 equals()는 '주소 비교'를 수행하지만, String 클래스에서 오버라이딩하여 '값 비교'로 동작
// 기준 문자열.equals("비교 문자열") => 값이 일치하면 true, 불일치하면 false 반환
```

📌 **중요한 개념**  
1️⃣ `==` → **객체의 참조(메모리 주소)**를 비교함   
2️⃣ `equals()` → **객체의 내용(값)**을 비교함  
3️⃣ `"abc"` 리터럴은 **String Pool에서 재사용됨**  
4️⃣ `new String("abc")`는 **Heap 메모리에 새로운 객체를 생성함**  

💡 **결론:**  
👉 **문자열 비교 시에는 `==`가 아니라 `equals()`를 사용해야 한다!**  

---

## 🎯 정리  
1️⃣ **String은 불변 객체**이며, 문자열을 변경하면 **새로운 객체가 생성됨**.   
2️⃣ **String은 String Pool을 활용하여 메모리 절약 가능**.  
3️⃣ **문자열 변경이 많으면 `StringBuilder` 또는 `StringBuffer`를 사용하는 것이 성능상 유리함**.  
4️⃣ **주요 메서드:** `length()`, `charAt()`, `equals()`, `substring()`, `replace()`, `split()` 등.  

📌 **String을 효율적으로 사용하려면 `StringBuilder`와의 차이를 이해하는 것이 중요!** 🚀







  
