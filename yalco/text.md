?? null 병합 연산자

!, +, -, ++, --, typeof
**
*, /, %
+, -


for of


let x = 0;
while(x < 14){
  const xNow = x++;

  if(xNow % 2 === 0) continue;
  if(xNow > 7) break;

  console.log(xNow);
}

do while = 일단 수행하고 조건을 평가


일급 객체의 특성


불변성

원시 타입 : 인자로 들어간 함수 내에서의 변경에 영향 X
--------> 실제 값이 아니라 복사된 값이 들어감

참조 타입 : 인자로 들어간 함수 내에서 요소가 변하면 실제로도 변함
--------> 복사된 값도 같은 객체나 배열을 가리키기 때문.

프로퍼티 삭제 - delete 연산자

메서드 - 펑션 생략 가능

const person = {
  name: '홍길동',

  paper (formal){
    return formal
    ? `안녕하십니까, ${this.name}입니다.`
    : `안녕하세요, ${this.name}이에요.`
  }
}
console.log(person.paper(true)); // 홍길동의 formal버전 자기소개 출력.

# 생성자 함수
 - 대문자로 시작함
 - new 연산자와 함께 사용.(그렇지 않으면 undefined 반환)
 - function으로 선언된 함수는 기본적으로 생성자 함수의 기능을 갖느다.

function Chicken(name, no){
  this.name = name;
  this.no = no;
  this.introduce = function(){
    return `안녕하세요. ${this.no}호 ${this.name}점입니다!`;
  }

  // new 생략 실수 방지하기
  if(!new.target){
    return new Chicken(name, no);
  }

}

const chain1 = new Chicken(`판교`, 3);
const chain2 = new Chicken(`강남`, 4);
const chain3 = new Chicken(`제주`, 5);

console.log(chain1, chain1.introduce());
console.log(chain2, chain2.introduce());
console.log(chain3, chain3.introduce());



# 클래스
 constructor 메서드
 인자를 받아 프로퍼티를 초기화함.
 클래스에 하나만 넣을 수 있음.


# 접근자 프로퍼티

getter, setter




#고차함수 메서드들

forEach
for문 대신 사용
예외를 던지지 않으면 종료할 수 없음(break, continue 사용 불가)

 



