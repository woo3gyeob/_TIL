# JAVA 복습 심화

<br>

#### **`자바 객체지향 프로그래밍`**

> 데이터를 추상화시켜 상태와 행위를 가진 객체로 만들고,
>
> 객체들 간의 유기적인 상호작용을 통해 로직을 구성하는 프로그래밍 기법

<br>

____

### 사용자 정의 함수

> 함수 = 메서드(method)
>
> 정해진 특정한 기능을 수행하는 모듈
>
> 함수는 각각의 모듈로서 쉽게 수정되고 보완

#### 세 개의 정수의 최대공약수

```java
public class Main {
	
	// 함수는 반환형, 함수명, 매개변수 순으로 작성
	public static int function(int a, int b, int c){
		int min;
		if(a > b){
			if(b > c){
				min = c;
			}
			else{
				min = b;
			}
		}
		else{
			if(a > c){
				min = c;
			}
			else{
				min = a;
			}
		}
		for(int i = min; i > 0; i--){
			if(a % i == 0 && b % i == 0 && c % i == 0){
				return i;
			}
		}
		return -1;
	}
	public static void main(String[] args) {
		
		System.out.println("(400, 300, 750)의 최대 공약수는 : " + function(400,300,750));
	}
}
// 출력
// (400, 300, 750)의 최대 공약수는 : 50
```

<br>

#### 3번째로 큰 약수

```java
public class Main {
	
	public static int function(int number, int k){
		int num = number / 2;
		while(k>0){
			if(number % num == 0){
				k--;
			}
			if(k == 0){
				return num;
			}
			num--;
		}
		return -1;
	}
	public static void main(String[] args) {
		int result = function(45, 3);
		if(result == -1){
			System.out.println("약수가 없습니다");
		}
		else{
			System.out.println("45의 약수 중 3번째로 작은 약수는 " + function(45, 3));
		}
	}
}
// 출력
// 45의 약수 중 3번째로 작은 약수는 5
```

<br>

#### 문자열에서 마지막 단어를 반환하는 함수

> **`string.charAt(k)`**  : string에서 k 인덱스의 문자를 반환

```java
public class Main {
	
	public static char function(String input){
		return input.charAt(input.length() - 1);
	}
	
	public static void main(String[] args) {
		System.out.println("Hello World의 마지막 단어는 " + function("Hello World"));
	}
}
// 출력
// Hello World의 마지막 단어는 d
```

<br>

#### max()를 활용해 최대값을 저장하는 함수

```java
public class Main {
	
	public static int max(int a, int b){
		return (a > b) ? a : b;
	}
	
	public static int function(int a, int b, int c){
		int result = max(a, b);
		result = max(result, c);
		return result;
	}
	
	public static void main(String[] args) {
		System.out.println("(345, 567, 789)중 가장 큰 값은 " + function(345,567,789));
	}
}
```

