---
title: 자바스크립트 간단 문법 정리
date: 2020-11-17 11:53:11
category: javascript
thumbnail: { thumbnailSrc }
draft: false
---

핀테크 아카데미 과정 수강 중 Node.js 배우기 전 간단하게 js 문법 정리 

## Node.Js란?

- 확장성 있는 네트워크 애플리케이션(특히 서버 사이드) 개발에 사용
- 작성 언어로 javascript를 활용

V8(자바스크립트 엔진) 위에서 동작하는 이벤트 처리 I/O 프레임워크이다. 웹 서버와 같이 확장성 있는 네트워크 프로그램 제작을 위해 고안되었다. 파이썬으로 만든 트위스티드, 펄로 만든 펄 객체 환경, 루비로 만든 이벤트머신과 그 용도가 비슷하다. 대부분의 자바스크립트가 웹 브라우저에서 실행되는 것과는 달리, 서버 측에서 실행된다. 일부 CommonJS 명세를 구현하고 있으며, 쌍방향 테스트를 위해 REPL 환경을 포함하고 있다.

## Node.Js 문법

### 변수 (Variables)

- 변수마다 자료형이 따로 정해져 있지 않다.

```jsx
var length = 16;  // Number
var lastName = "Johnson";   // String

//#in java
//public int length = 16;
//public String lastName = "John";

var x = { firstName: "John", lastName: "Doe"};  // Object
var x = 16 + "Volvo";
console.log(x);
var y = "16" + "Volvo";
console.log(y);
var z = 16 + "Volvo";
console.log(z);
var a = "Volvo" + 16;
console.log(a);
var b = 16 + 4 + "Volvo";
console.log(b);
```

<br/>

### 연산자 (Operator)

- 사칙연산 (+, -, *, /)

```jsx
var x = 5; // assign the value 5 to x
var y = 2; // assign the value 2 to y
var z = x + y; // assign the value 7 to z (x + y)
var a = x - y;
var b = x * y;
var c = x / y;
console.log("x: " + x);
console.log("y: " + y);
console.log("z: " + z);
console.log("a: " + a);
console.log("b: " + b);
console.log("c: " + c);
```

<br/>

### 메소드, 펑션(function)

```jsx
function multi(p1, p2) {
	return p1 * p2; // p1, p2 곱연산의 결과를 반환한다.
}

//#work 1 더하기, 나누기, 빼기 기능 작성
function plus(p1, p2) {
	return p1 + p2;
}

function minus(p1, p2) {
	return p1 - p2;
}

function divide(p1, p2) {
	return p1 / p2;
}

console.log(multi(2,6));
console.log(plus(2,6));
console.log(minus(2,6));
console.log(divide(2,6));
```

<br/>

### 객체(Object)

```jsx
var car = { 	
		name : "sonata", 	
		ph : "500ph", 	
		start : function () { 		
			console.log("engine is starting"); 	
		}, 	
		stop : function () { 		
			console.log("engine is stoped"); 
		} 
}

var car2 = {
    name : "Avante",
    ph : "400ph",
    start : function () { 
			console.log('insert keys');		
			console.log("engine is starting"); 	
		}, 	
		stop : function () { 		
			console.log("engine is stoped"); 
		} 
}

console.log(car.name);
car.start();

console.log(car2.name);
car2.start();
```

<br/>

### 배열(Array)

```jsx
var car1 = "Saab";
var car2 = "Volvo";
var car3 = "BMW";
var cars = ["Saab", "Volvo", "BMW"];

console.log(cars);
console.log(cars[0]);
console.log(cars[1]);
console.log(cars[2]);
```

```jsx
var car1 = { 	
		name : "sonata", 	
		ph : "500ph", 	
		start : function () { 		
			console.log("engine is starting"); 	
		}, 	
		stop : function () { 		
			console.log("engine is stoped"); 
		} 
}

var car2 = {
    name : "Avante",
    ph : "400ph",
    start : function () { 
			console.log('insert keys');		
			console.log("engine is starting"); 	
		}, 	
		stop : function () { 		
			console.log("engine is stoped"); 
		} 
}

var cars = [car1, car2];
console.log(cars);
```

<br/>

### 반복문(for-loop)

```jsx
var cars = ["BMW", "Volvo", "Saab", "Ford", "Fiat", "Audi"];
var text = "";
var i;
for(i = 0 ; i < cars.length; i++) {
		text += cars[i];
}
console.log(text);

cars.map((car)=>{
    console.log(car);
})
```

<br/>

### 조건문(if-else)

```jsx
var hour = 12;
var greeting = "좋은 아침 입니다";

if(hour < 18) {
	greeting = "Good day";
}

console.log(greeting);
```

```jsx
var car1 = { 	
		name : "sonata", 	
		ph : "500ph", 	
		start : function () { 		
			console.log("engine is starting"); 	
		}, 	
		stop : function () { 		
			console.log("engine is stoped"); 
		} 
}

var car2 = {
    name : "Avante",
    ph : "400ph",
    start : function () { 
			console.log('insert keys');		
			console.log("engine is starting"); 	
		}, 	
		stop : function () { 		
			console.log("engine is stoped"); 
		} 
}

var car3 = {
    name : "BMW",
    ph : "400ph",
    start : function () { 
			console.log('insert keys');		
			console.log("engine is starting"); 	
		}, 	
		stop : function () { 		
			console.log("engine is stoped"); 
		} 
}

// work3 자동차 이름이 BMW가 있으면 '!' 출력 (for / if)
var cars = [car1, car2, car3];
var i;
for(i = 0 ; i < cars.length; i++){
	if(cars[i].name == "BMW")
		console.log('!');
}
```