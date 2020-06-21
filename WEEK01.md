# [1주차] : UI Interaction Senior
JavaScript 프로그래밍의 심화 부분(scope hoist, closure 등) 개념을 정리하고, 원리 및 작동 방식을 학습합니다.
---------------------------------------
## 1. Scope(변수 범위)
[Scope](https://app.gitbook.com/@jmk/s/workspace/undefined-2/1.-1)

### Rule 1 : Local Scope vs Global Scope
- 안쪽 Scope에서 바깥 변수/함수를 접근하는 것은 가능
- 바깥쪽 Scope에서 안쪽 변수/함수를 접근하는 것은 불가능
- Scope는 중첩이 가능합니다.(함수 안에 함수 가능)
- Global Scope(전역 변수)는 어디서는 접근이 가능합니다.
- 지역 변수는 함수 내에서 전역 변수보다 더 높은 우선순위를 가집니다.

### Rule 2 : Function Scope vs Block Scope
- var 는 Javacript에서 변수를 선언하는 유일한 방식(코드의 일관성을 해치기 때문에 사용 지양) Function Scope
- let과 const는 Block Scope이며, const는 값을 재정의 할 수 없음.

### Rule 3 : 전역 변수와 window 객체
- 전역 범위를 대표하는 객체 window
- Global Scope에서 선언된 함수, 그리고 var 키워드를 이용해 선언된 변수는 window 객체와 연결됨.
```
var myName = 'Tony';
console.log(window.myName); // Tony

function foo() {
    console.log('bar');
}
console.log(foo === window.foo); // true
```

### Rule 4 : 선언 없이 초기화된 전역 변수
- 자바스크립트의 유연성 때문에 오류가 나지 않지만 일관성을 위해 'use strict'를 사용합니다.

## 2. 연산자 x 조건 처리

### 비교 연산자
- 동등(==) : 피연산자들이 같으면 참을 반환
- 부등(!=) : 피연산자들이 다르면 참을 반환
- 일치(===) : 피연산자들이 같고 피연산자들의 같은 형태인 경우 참을 반환
- 불일치(!==) : 피연산자들이 다르거나 형태가 다른 경우 참을 반환
- ~보다 큰(>) : 좌변의 피연산자보다 우변의 피연산자가 크면 참을 반환
- ~보다 크거나 같음(>=) : 좌변의 피연산자 보다 우변의 피연산자가 크거나 같으면 참을 반환
- ~보다 작음(<) : 좌변의 피연산자 보다 우변의 피연산자가 작으면 참을 반환
- ~보다 작거나 같음(<=) : 좌변의 피연산자 보다 우변의 피연산자가 작거나 같으면 참을 반환

### 논리 연산자
- AND(&&)
```
true && true //true
true && false //false
false && true //false
```
- OR(||)
```
true || true //true
true || false //true
false || true //true
false || false //false
```
- NOT(!)
```
!true //false
!false //true
!!true //true
```

### typeof
- 데이터타입을 검출할때 주로 사용
- array와 null은 제대로 작동 하지 않음. [배열의 경우 Array.isArray()를 통해 데이터타입을 검출]

## nodeType
- 노드타입은 상수로 이루어져 있으며, 대문자로 구별된다.
- 변수선언의 const가 Constants의 앞글자이다.
- Node.ELEMENT_NODE === 1
- Node.TEXT_NODE === 3
- Node.DOCUMENT_NODE === 9
