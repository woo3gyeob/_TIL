# JAVA 복습

<br>

#### `오버플로우`

```java
// int 최대값 : 2147483647 (약 -21억 ~ 21억)
public class Main {
    
	// final static : 전역상수
	final static int INT_MAX = 2147483647;
	
	public static void main(String[] args) {
		
		int a = INT_MAX;
		System.out.println(a);
		
	}

}
// 2147483647
```

<br>

int 타입이 가질 수 있는 최대, 최소 값을 벗어나는 경우, 반대로 돌아가게 됨

```java
public class Main {
	
	final static int INT_MAX = 2147483647;
	
	public static void main(String[] args) {
		
		int a = INT_MAX;
		System.out.println(a+1);
		
	}

}
// 2147483647(int 최대값) + 1 = -2147483647(int 최소값)
// -2147483647
```

<br>

### 자바 변수 관련 상식

___

- 자바는 변수 초기화를 하지 않으면 사용 불가
- 정수를 나타내는 타입으로는 short, int, long으로 다양
- 정수형 변수에 실수값 넣으면 정수부분만 저장

```java
// 실수값의 정수형 선언
public class Main {
	
	public static void main(String[] args) {
		
		int a = (int) 0.5;
		System.out.println(a);
	}
}

// 출력
0
```

- 실수값을 반올림할 때는 변수에 0.5를 더해서 정수형으로 형변환하면 된다

- 반올림한 값 = (int) (실수 + 0.5)

```java
public class Main {
	
	public static void main(String[] args) {
		
		double b = 0.6;
		int a = (int) (b + 0.5);
		System.out.println(a);
    }
}
```

<br>

### 자료형

___

> String, Array, boolean, char, int, double
>
> String형의 편리성 : `substring`

```java
// 아스키 코드 기반의 char 활용
문자 출력
public class Main {
	
	public static void main(String[] args) {
		
		for(char i = 'a'; i <= 'z'; i++){
			System.out.print(i + " ");
		}
	}
}
// 출력
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

<br>

#### `형식지정자` : %o, %x

**System.out.format()**

```java
public class Main {
	
	public static void main(String[] args) {
		
		int a = 200;
		
		System.out.println("10진수 : " + a);
		System.out.format("8진수 : %o\n", a);
		System.out.format("16진수 : %x", a);
	}
}
// 출력
10진수 : 200
8진수 : 310
16진수 : c8
```

<br>

### `substring`

```java
public class Main {
	
	public static void main(String[] args) {
		
		String name = "John Doe";
		System.out.println(name);
		System.out.println(name.substring(0, 1));
		System.out.println(name.substring(3, 6));
	}
}
// 출력
John Doe
J
n D
```

<br>

### `자료형 정리`

> 정수를 나타내는 자료형이 많은 이유 : 각 자료형이 차지하는 메모리 공간의 크기가 다르기 때문
>
> double 형이라고 해도 큰 수 저장시 잘못된 결과 나올 수 있음
>
> 소수점 표기 형식을 지수 형식으로 출력하고 싶으면 **%e**를 이용할 수 있다
>
> String 최대 크기는 무한
>
> 자바의 String은 **클래스 기반의 비원시적인 자료형**

<br>

<br>

### 연산자

___

> +, - ,* ,/ ,%(나머지)

```java
public class Main {
	
	final static int SECOND = 1000;
	
	public static void main(String[] args) {
		
		int minute = SECOND / 60;
		int second = SECOND % 60;
		System.out.println(minute + "분 " + second + "초");
	}
}
// 출력
16분 40초
```

<br>

#### 증감연산자

```java
public class Main {
	
	public static void main(String[] args) {
		
		int a = 10;
		System.out.println("현재의 a값 : " + a + "입니다");
		a++;
		System.out.println("현재의 a값 : " + a + "입니다");
		System.out.println("현재의 a값 : " + ++a + "입니다");
		System.out.println("현재의 a값 : " + a++ + "입니다");
		System.out.println("현재의 a값 : " + a + "입니다");
	}
}
// 출력
현재의 a값 : 10입니다
현재의 a값 : 11입니다
현재의 a값 : 12입니다
현재의 a값 : 12입니다
현재의 a값 : 13입니다
```

<br>

#### modular 연산

```java
public class Main {
	
	public static void main(String[] args) {
		
		System.out.println(1 % 3);
		System.out.println(2 % 3);
		System.out.println(3 % 3);
		System.out.println(4 % 3);
		System.out.println(5 % 3);
		System.out.println(6 % 3);
	}
}
// 출력
1
2
0
1
2
0
```

<br>

```java
public class Main {
	
	public static void main(String[] args) {
		
		int a = 50;
		int b = 50;
		
		System.out.println("a와 b가 같을까? : " + (a == b));
		System.out.println("a와 b보다 클까? : " + (a > b));
		System.out.println("a가 b와 같으면서 a가 30보다 큰가요? : " + ((a == b) && (a > 30)));
		System.out.println("a가 50이 아닐까? : " + !(a == 50));
		
	}
}
//출력
a와 b가 같을까? : true
a와 b보다 클까? : false
a가 b와 같으면서 a가 30보다 큰가요? : true
a가 50이 아닐까? : false
```

<br>

### 삼항연산자

```java
public class Main {
	
	public static void main(String[] args) {
		
		int x = 50;
		int y = 60;
		
		System.out.println("최댓값은 " + max(x,y) + "입니다.");
	}
	// 함수는 반환형, 함수 이름, 매개변수로 구성
	static int max(int a, int b){
		int result = (a > b) ? a : b; //삼항연산자. a가 b보다 크면 a, 아니면 b 반환
		return result;
	}
}
// 출력
최댓값은 60입니다.
```

#### pow

```java
public class Main {
	
	public static void main(String[] args) {
		
		double a = Math.pow(3.0, 20.0);
		System.out.println("3의 20제곱은 " + (int) a + "입니다.");
				
	}
	
}
// 출력 
3의 20제곱은 2147483647입니다.
```

<br>

<br>

## 조건문, 반복문

#### `조건문 if`

1) 대소비교

```java
public class Main {
	
	public static void main(String[] args) {
		
		int score = 95;
		if(score >= 90){
			System.out.println("A+");
		}
		else if(score >= 80){
			System.out.println("B+");
		}
		else{
			System.out.println("C+");
		}
	}	
}
// 출력
A+
```

2) 문자열의 `contains()` 활용

```java
public class Main {
	
	public static void main(String[] args) {
		
		String a = "I love You";
		if(a.contains("love")) {
			// 포함하는 경우, 실행되는 부분
			System.out.println("Me too.");
		}else{
			// 포함하지 않은 경우, 실행되는 부분
			System.out.println("I hate you");
		}
	}
}
// 출력
Me too.
```

3) 문자열의 동일여부 비교는 **`string.equals("대상문자열")`** 을 사용한다

​    문자열을 대/소문자와 상관없이 같은지 비교할 때는 **`string.equalsIgnoreCase("대상문자열")`** 사용

```java
public class Main {
	
	public static void main(String[] args) {
		
		String a = "man";
		int b = 0;
		
		// 자바는 String을 비교할 때 equal()을 이용한다
		// 그 이유는 String은 다른 자료형과 다른 문자열 자료형이기 때문이다
		if(a.equals("man")){
			System.out.println("남자입니다");
		}
		else{
			System.out.println("여자입니다");
		}
		if(b == 0){
			System.out.println("b는 0입니다");
		}
		else{
			System.out.println("b는 0이 아닙니다");
		}
		if(a.equalsIgnoreCase("Man")){
			System.out.println("대소문자 상관없이 같습니다");
		}
	}
	
}
```

<br>

#### `반복문`

##### while

```java
public class Main {
	
	public static void main(String[] args) {
		
		int i = 1, result = 0;
		while(i<1001){
			result += i++;
		}
		System.out.println("1부터 1000까지의 합은 " + result);
	}
}
// 출력
1부터 1000까지의 합은 500500
```

#### for

```java
public class Main {
	
	final static int N = 5;
	
	public static void main(String[] args) {
		
		// for문: 초기화부분, 조건 부분, 연산 부분
		for(int i = N; i > 0; i--){
			
			for(int j=i; j>0; j--){
				System.out.print(j + " ");
			}
			System.out.println();
		}
	}
}
// 출력
5 4 3 2 1 
4 3 2 1 
3 2 1 
2 1 
1 
```

이중 for문으로 원 출력하기

```java
public class Main {
	
	static final int N = 15;
	
	public static void main(String[] args) {
		
		// x^2 + y^2 = r^2
		for(int i = -N; i <= N; i++){
			for(int j = -N; j <= N; j++){
				if(i*i + j*j <= N*N){
					System.out.print("*");
				}
				else{
					System.out.print(" ");
				}
			}
			System.out.println();
		}
		
	}
}
// 출력
               *               
          ***********          
        ***************        
      *******************      
     *********************     
    ***********************    
   *************************   
   *************************   
  ***************************  
  ***************************  
 ***************************** 
 ***************************** 
 ***************************** 
 ***************************** 
 ***************************** 
*******************************
 ***************************** 
 ***************************** 
 ***************************** 
 ***************************** 
 ***************************** 
  ***************************  
  ***************************  
   *************************   
   *************************   
    ***********************    
     *********************     
      *******************      
        ***************        
          ***********          
               *               
```

break 활용

```java
public class Main {
	
	public static void main(String[] args) {
		
		int count = 0;
		for(;;){
			System.out.print(count + " ");
			count++;
			if(count == 10){
				break;
			}
		}
		
	}
}
// 출력
0 1 2 3 4 5 6 7 8 9 
```

<br>

<br>

## 기본 입출력

#### `Scanner 클래스`

#### 정수 입력

```java
import java.util.Scanner;

public class Main {
	
	public static void main(String[] args) {
		
		Scanner sc = new Scanner(System.in);
		System.out.print("정수를 입력하세요 : ");
		int i = sc.nextInt();
		System.out.println("입력된 정수는 : " + i + "입니다");
		sc.close();
	}
}
// 출력
정수를 입력하세요 : 
123
입력된 정수는 : 123입니다
```

<br>

#### 파일 입력

> sc.hasNextInt() : 다음 입력 정수가 있는지 (boolean)
>
> sc.nextInt() : 정수 입력 받기

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class Main {
	
	public static void main(String[] args) {
		
		File file = new File("input.txt");
		try {
			Scanner sc = new Scanner(file);
			while(sc.hasNextInt()){
				System.out.println(sc.nextInt() * 100);
			}
		} catch (FileNotFoundException e) {
			// TODO Auto-generated catch block
			System.out.println("파일을 읽어오는 도중 오류 발생!");
		}
		
	}
}
```

<br>

Scanner로 문자열을 입력 받고 싶을 때는 next()와 nextline() 함수를 적절히 활용 가능



















