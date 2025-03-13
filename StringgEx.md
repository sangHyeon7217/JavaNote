Java String Concatenation: 연결 연산자

Example
String firstName = "John";
String lastName = "Doe";
System.out.println(firstName + " " + lastName);

String Special Characters

Because strings must be written within quotes, Java will misunderstand this string, and generate an error:

String txt = "We are the so-called "Vikings" from the north.";

Escape character	Result	Description
\'	'	Single quote
\"	"	Double quote
\\	\	Backslash

Example
String txt = "We are the so-called \"Vikings\" from the north.";

 ![String클래스의 생성자와 메서드](StringClassMethod.png)
 
 %imutable: 불변 ->String 인스턴스의 내용은 바꿀 수 없다
 
  
