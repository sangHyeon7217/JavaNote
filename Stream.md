## Stream

### OutputStream
`OutputStream`은 데이터를 파일로 출력할 때 사용됩니다.

```java
package ch13;

import java.io.*;
public class OutputStream01 {
    public static void main(String[] args) throws FileNotFoundException, IOException {
        OutputStream os = new FileOutputStream("D:\\javaStudy\\test02.db");
        byte[] arr= {10,20,30,40,50,60,70};
        
        // os.write(arr);  // byte[] arr에 있는 모든 데이터를 보낸다
        os.write(arr, 1, 3); // byte[] arr에 있는 arr[1]부터 3개를 보낸다
        
        os.flush(); // 버퍼 비우기
        os.close(); // 스트림 닫기
        
        System.out.println("완료");
    }
}
```

### InputStream
`InputStream`은 파일에서 데이터를 읽어올 때 사용됩니다.

```java
package ch13;

import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;
import java.io.InputStream;

public class InputStream01 {
    public static void main(String[] args) {
        try {
            InputStream os = new FileInputStream("D:\\javaStudy\\214124test02.db");
        } catch(IOException e) {
            System.out.println("IOException 발생: " + e.getMessage());
        }
    }
}
```

---

## 📌 try-catch-finally 설명  

| 키워드  | 설명 |
|---------|------------------------------------|
| `try`   | 예외가 발생할 가능성이 있는 코드 블록 |
| `catch` | 예외가 발생하면 실행되는 코드 블록 |
| `finally` | 예외 발생 여부와 관계없이 항상 실행되는 코드 블록 (리소스 정리 등에 사용) |

📌 `finally` 블록은 생략 가능하지만, **파일/데이터베이스 연결을 닫을 때 유용**하게 사용됩니다.

---

## 📌 최종 정리
1️⃣ `FileNotFoundException`은 파일이 존재하지 않을 때 발생하는 예외  
2️⃣ `try-catch` 문을 사용하여 예외를 처리해야 프로그램이 비정상 종료되지 않음  
3️⃣ `finally` 블록을 활용하면 파일을 안전하게 닫을 수 있음  
4️⃣ 파일을 다룰 때는 예외 처리를 반드시 수행해야 함 🚀