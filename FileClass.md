# File 클래스 개요

`File` 클래스는 Java에서 파일과 디렉터리를 다룰 때 사용하는 클래스입니다. `java.io` 패키지에 속해 있으며, 파일의 생성, 삭제, 정보 확인, 디렉터리 탐색 등을 수행할 수 있습니다.

## 📌 주요 특징
- **패키지**: `java.io`
- **역할**: 파일 및 디렉터리 조작
- **파일을 직접 읽거나 쓰는 기능은 없음** (파일 스트림과 함께 사용해야 함)

## 📌 주요 생성자
```java
// 특정 경로의 파일을 나타내는 File 객체 생성
File file1 = new File("example.txt");

// 디렉터리와 파일명을 분리해서 지정
File file2 = new File("C:\\Users", "example.txt");

// 부모 File 객체와 하위 파일명을 조합
File parentDir = new File("C:\\Users");
File file3 = new File(parentDir, "example.txt");
```

## 📌 주요 메서드

| 메서드 | 설명 |
|--------|------|
| `exists()` | 파일이나 디렉터리가 존재하는지 확인 |
| `createNewFile()` | 파일을 생성 (이미 존재하면 `false` 반환) |
| `delete()` | 파일 또는 디렉터리 삭제 |
| `isFile()` | 파일인지 여부 확인 |
| `isDirectory()` | 디렉터리인지 여부 확인 |
| `length()` | 파일 크기 반환 (byte 단위) |
| `getName()` | 파일 이름 반환 |
| `getPath()` | 전체 경로 반환 |
| `getAbsolutePath()` | 절대 경로 반환 |
| `mkdir()` | 디렉터리 생성 |
| `mkdirs()` | 필요한 상위 디렉터리까지 포함하여 생성 |
| `listFiles()` | 디렉터리 내 파일 목록을 `File[]`로 반환 |

## 📌 사용 예제

### 1️⃣ 파일 생성 및 정보 확인
```java
import java.io.File;
import java.io.IOException;

public class FileExample {
    public static void main(String[] args) {
        try {
            File file = new File("test.txt");
            
            if (file.createNewFile()) {
                System.out.println("파일 생성됨: " + file.getAbsolutePath());
            } else {
                System.out.println("파일이 이미 존재함.");
            }

            System.out.println("파일 이름: " + file.getName());
            System.out.println("파일 경로: " + file.getPath());
            System.out.println("절대 경로: " + file.getAbsolutePath());
            System.out.println("파일 크기: " + file.length() + " 바이트");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

### 2️⃣ 디렉터리 생성 및 파일 목록 확인
```java
import java.io.File;

public class DirectoryExample {
    public static void main(String[] args) {
        File dir = new File("myDirectory");

        if (!dir.exists()) {
            if (dir.mkdir()) {
                System.out.println("디렉터리 생성됨: " + dir.getAbsolutePath());
            }
        }

        File[] files = dir.listFiles();
        if (files != null) {
            System.out.println("디렉터리 내 파일 목록:");
            for (File file : files) {
                System.out.println("- " + file.getName());
            }
        }
    }
}
```

### 3️⃣ 파일 삭제
```java
import java.io.File;

public class DeleteFileExample {
    public static void main(String[] args) {
        File file = new File("test.txt");

        if (file.exists()) {
            if (file.delete()) {
                System.out.println("파일 삭제됨.");
            } else {
                System.out.println("파일 삭제 실패.");
            }
        } else {
            System.out.println("파일이 존재하지 않음.");
        }
    }
}
```

## 📌 `File` 클래스의 한계
- 파일의 내용을 읽거나 쓰는 기능이 없음 (`FileReader`, `FileWriter`, `BufferedReader` 등의 스트림을 사용해야 함)
- `createNewFile()`은 파일이 이미 존재하면 새로운 파일을 생성하지 않음 (덮어쓰기하려면 `FileWriter` 사용)
- `delete()`는 디렉터리가 비어 있어야 삭제 가능 (비어 있지 않으면 `delete()` 실패)

## 📌 요약
- `File` 클래스는 파일과 디렉터리를 다룰 수 있지만, **파일 내용을 직접 다루지는 못함**
- **파일 존재 여부 확인, 경로 반환, 디렉터리 생성 및 목록 조회 등의 작업에 사용**
- **파일 읽기/쓰기 작업은 `FileReader`, `FileWriter`, `BufferedReader` 등과 함께 사용**

이제 `File` 클래스를 직접 사용해 보고 익숙해지는 것이 중요합니다! 🚀

