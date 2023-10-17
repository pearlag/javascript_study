변수를 선언하는 규칙

이름은 의미있게
카멜케이스로
첫 글자는 반드시 문자나 밑줄, $로 시작해야 한다.




변수 선언과 값/식 할당

var 다음에 변수 이름을 적음 (변수 선언)
변수 오른쪽에 = 기호를 붙이고 오른쪽에 저장할 값이나, 식을 작성
변수는 선언과 동시에 초기화하는 습관을 들여야  한다.




function calc(age, s)  여기서 age,s는 매개변수,파라메터,인자값,아규먼츠







자료형

기본형
number :: 따옴표 없이 표기한 숫자
string :: ""로 묶어 나타냄
boolean :: 논리자료형. 참과 거짓 두 가지 유형만.
undefined :: 자료형을 지정하지 않았을 때
null :: 값이 유효하지 않을 때
복합형
array :: 하나의 변수에 여러 값을 저장함
object :: 함수와 속성이 함께 포함됨.




자료형의 특징

느슨한 자료형 체크
미리 변수의 자료형을 지정하지 않는다.
변수를 지정하고 원하는 값을 할당만 하면 된다.







배열(array)

하나의 변수에 여러 값 저장
배열의 인덱스는 0부터 시작 (n-1)
배열에 있는 값을 가져오려면 배열 이름과 대괄호 안에 인덱스 사용.

langth의 값도 구할 수 있다.

var seasons ["봄", "여름", "가을", "겨울" ];

seasons[0]
"봄"

seasons[1]
"여름"

seasons[2]
"가을"

seasons[3]
"겨울"







객체

여러 자료를 중괄호{}로 묶은 것.
key와  value를 한 쌍으로 여러 자료 저장.




var kim{
	firstName: "John",
	lastName: "Kim",
	age: 35,
	address: "seoul"
}










산술자




사칙 연산자
나머지 연산자
증감 연산자
할당 연산자
값을 누적할 때 사용
연결 연산자
형변환
숫자형과 문자형을 더하면 숫자를 문자열로 인식함.
곱하기나 나누기, 나머지 연산에서는 문자형 자료를 모두 숫자로 자동 인식함.










조건문

if문





if(조건식. boolean값이어야 함){
  // 명령  
}




괄호 안의 조건이 true이면 {} 사이의 명령을 처리하고, false면 명령 무시.

중첩 if문(nested if문)도 가능하다.




if .. else 문




if (a == "여자") {
 // 명령
}else{
 // 명령
}





if문 괄호 안의 조건이 true면 if 다음의 {} 명령 처리, false면  else 다음의 {}명령 처리




// A
if(score >= 90){

}else if(score >= 80){

}else if(score >= 70){

}else{

}

// B

if(score >= 90){

}if(score >= 80){

}if(score >= 70){

}else{

}

// A와 B의 차이는?
결과는 같지만.
A : CPU가 if문에 하나하나 다 참조를 하게 된다. 효율성이 떨어진다.
B : 값에 따라 cpu가 if구문을 최소한으로 참조하게 된다.













조건 연산자

조건이 하나이고 실행할 명령도 하나일 때

피연산자가 3개일 때 삼항 연산자라고도 부름.

var score = 75;
(score >=60) ? alrert("통과") : alert("실패");
   조건   / 조건이 true일때 실행/ false일때 실행







switch문으로 여러 조건 값 확인하기

switch → case → break → default

var session = prompt("관심 세션을 선택해 주세요. 1-마케팅, 2-개발, 3-디자인", "1"); // 기본값으로 1 넣음

switch(session){
	case "1" : document.write("<p>마케팅 세션은 201호에서 진행됩니다.</p>");
		break; // switch 문 빠져나오기.
	case "2" : document.write("<p>개발 세션은 202호에서 진행됩니다.</p>");
		break;
 	case "3" : document.write("<p>디자인 세션은 203호에서 진행됩니다.</p>");
		break;
	default: alert("잘못 입력했습니다."); // default는 옵션임.

}
한정된 데이터값으로 조건문을 만들 때 사용한다.(가독성 좋음) 그러나 보통 현업에서는 if문으로 쓴다. 왜냐하면 데이터가 정해져있는 경우가 잘 없기 때문이다.
모든 switch문은 if문으로 변경이 가능하지만, 그 반대는 불가하다. 







반복문

for ( 반복 횟수 기준이라면 )
var sum = 0;

for(var i = 1; i< 6; i++){
	sum += i; // sum = sum + i;
}




카운터 변수를 기준으로 명령을 여러 번 실행하기.

코드를 간단하게 작성할 수 있음, 실행 속도 빨라짐.

for 문 중첩

두 개 이상의 for문을 중첩해서 사용할 때, 먼저 실행하는 for문을 안쪽에, 나중에 실행하는 for문을 바깥쪽에 작성.

//구구단 프로그램
for (var i = 2; i <= 9; i++){ // 2에서 9단까지 i 증감 // 나중에 실행하는 for문
	document.write("<div>");
	document.write("<h3>" + i + "단</h3>");
	for(var j = 1; j <= 9; j++){ // 각 단의 구구단 실행 (1부터 9까지 곱함). 10이 되면 빠져나오고 초기화됨 // 먼저 실행하는 for문
		document.write(i + "X" + j + " = " + i * j + "<br />");
	}
	document.write("</div>");


}









while문, do...while문 ( 특정 조건에 따라 반복한다면! //  )
//while // 무한루프 전용 // 처음부터 false일수도 있다. // false를 반드시 만들어야한다.

var i = 0
while (i < 10){
	document.write('반복 조건이 true이면 반복한다.<br />');
	i += 1;
}






//do .. while // 사용자에게 일단 물어보는 프로그램에서 많이 사용된다. ex. 계속 하시겠습니까? // 최소 한 번은 실행된다.

var i = 0
do {
 	document.write('반복 조건이 true이면 반복한다.<br />'); //일단 명령 실행
	i += 1;
}while (i < 10); // 조건이 false가 되면 반복 종료










함수 선언 

function A(){

}




함수 호출(함수 실행)

A()




매개변수(파라미터, 인자값)

function A(매개변수){

}




인수(argument)

함수를 실행하기 위해 필요하다고 지정하는 값

함수를 실행할 때 매개변수로 넘겨주는 값

A(인수);




return문

함수를 실행한 결과값을 함수 밖으로 넘기는 문

반환된 값은 함수를 호출한 곳으로 넘어감




스코프(scope)

변수를 선언하고 사용할 때 변수가 적용되는 범위




지역 변수(local variable)

변수를 선언한 함수에서만 사용할 수 있는 변수. 블럭 안에서만 허용된다.




전역 변수(global variable)

소스 전체에서 사용할 수 있는 변수

함수 내에서 전역 변수를 선언하려면 예약어 없이 선언(이미 선언된 변수 위에 덮어쓸수도 있다)




익명 함수




즉시 실행 함수







이벤트

마우스 이벤트
click : 눌렀을 때
dbclick : 두 번 눌렀을 때
mousedown : 누르는 동안
mousemove : 포인터를 움직일 때
mouseover : 포인터가 요소 위로 옮겨질 때
mouseout : 포인터가 요소를 벗어날 때
mouseup : 마우스 버튼에서 손을 뗄 때
키보드 이벤트
keypress : 키를 눌렀을 때
keydown : 키를 누르는 동안
keyup : 키에서 손을 뗄 때
폼 이벤트
blur : 폼 요소에 포커스를 잃었을 때
change : 목록이나 체크 상태 등이 변경되었을 때 :: input, select, textarea ..
focus : 폼 요소에 포커스가 놓였을 때 :: label, select, textarea, button
reset : 폼이 다시 시작되었을 때
submit : submit 버튼을 눌렀을 때
문서 로딩 이벤트
abort : 웹 문서가 완전히 로딩되기 전에 불러오기를 멈췄을 때
error : 문서가 정확히 로딩되지 않았을 때
load : 문서 로딩이 끝나면
resize : 문서 화면 크기가 바뀌었을 때
scroll : 문서 화면이 스크롤되었을 때
unload : 문서를 벗어날 때




ready() load() 차이점
ready() : 이벤트는 클라이언트가 사이트를 방문할 때 요청한 HTML문서. 객체의 로딩이 끝나면 이벤트를 실행한다.
 load() : 외부 리소스의 로딩이 끝나면 이벤트를 실행한다.







함수의 종류




함수의 분류

사용자 정의 함수

사용자가 필요한 기능을 직접 만든 함수를 말한다.
자바스크립트 코어 함수
자바스크립트가 기본적으로 제공하는 함수
parseInt, Math.random 등




사용 방법에 따른 함수 종류

일반 함수
중첩 함수
함수 내부에 만들어지는 함수를 중첩 함수라 칭한다.




function outter(){
	function inner(){
		document.write("inner()호출됨");
	}
	inner();
}
outter();




용도

이름이 없는 이벤트 리스너로 많이 활용된다.

클릭 이벤트 리스너가 중첩 함수로 사용된 형태

$(function(){
	$(".btn").click(function(){
		alert("안녕하세요");
	});

});




중복 코드 또는 그룹화
함수 내부의 커다란 기능이나 중복 코드를 내부 함수로 만들어 재사용한다.
외부 함수와 내부 함수의 아주 밀접한 관계일 때 사용하는 것이 좋다.
중첩 함수와 중첩함수를 포함한 함수와의 관계
중첩 함수에서 중첩함수를 포함하고 있는 함수의 지역변수에 접근해서 사용할 수 있다.







콜백 함수
함수 실행 결과 값을 리턴이 아닌 매개변수로 넘어온 함수를 호출해서 넘겨주는 방식을 콜백이라 하며, 이 때 매개변수로 넘어온 값을 콜백함수라 한다.




function name(callback){
	로직 구현 부분
	로직 처리 부분
	callback();
}







클로저 함수
보통, 함수 호출에 의해 함수 내부의 실행구문을 모두 실행하게 되면 함수 내부에서 만든 지역변수가 자동으로 사라지지만, 어떤 경우에는 사라지지 않고 남는 경우가 존재한다. 이 현상을 클로저라고 한다.




function name(){
	var count = 1; // 일반 함수는 사라짐
	$(".btn").on("click", function(){ // 클로저 함수는 사라지지 않음. 클릭할 때마다 나타나야 하기 때문에.
		count++;
		alert(count);
	});
}






함수 리터럴
그 자체로서의 값을 의미한다.

마치 변수 name을 함수로써 사용 가능하다.

var name = function(){
	//
}





자바스크립트 코어 라이브러리



타이머 함수 : 전역 객체인 window에 포함되어있다.
setInterval() : 일정 시간마다 주기적으로 특정 구문을 실행
var A = setInterval(func, duration);
func: 지연 시간마다 타이머 함수에 의해 호출되는 콜백 함수
duration: 지연 시간, 밀리초.(1000 = 1초 , 100 = 0.1초 )
$(function(){
     var $contents = $("#contents");
     var cnt = 0;
 
     //익명함수 풀이
     setInterval(function(){
       cnt++; // 값을 증가
       $contents.text(cnt); // text()를 이용하여 div영역에 출력.
     }, 1000); // 1초마다 반복
 
     //일반함수풀이
     function addCnt(){
       cnt++;
       $contents.text(cnt); // text()를 이용하여 div영역에 출력.
     }
     setInterval(addCnt, 1000);
});
setTimeout() : 일정 시간이 지난 후 특정 구문을 딱 한 번 실행
var A = setTimeout(func, duration)
$(function(){
      var $contents = $("#contents");
 
      //익명함수 풀이
      //setTimeout는 duration밀리초 후에 단 한 번만 실행이 되는 함수
      setTimeout(function(){
        $contents.text("안녕하세요"); // text()를 이용하여 div영역에 출력.
      }, 3000); // 1초마다 반복
      
 
      //일반함수풀이
      function addCnt(){
        $contents.text("안녕하세요"); // text()를 이용하여 div영역에 출력.
      }
      setTimeout(addCnt, 3000);
 
 });
clearInterval():실행 중인 타이머 함수를 멈추는 기능
clearInterval(A) // A:제거할 타이머 네임.
$(function(){
      var $contents = $("#contents");
      var cnt = 0;
      var timerID = 0;
 
      //익명함수 풀이
      timerID = setInterval(function(){
        cnt++;
        $contents.text(cnt);
      }, 1000); // 1초마다 반복
 
      $("#stop").click(function(){
        clearInterval(timerID);
        console.log("멈췄습니다.");
      });
 
 
      //일반함수풀이
      function addClock(){
        timerID = setInterval(function(){
            cnt++;
            $contents.text(cnt);
          }, 1000);
      }
   
      addClock();
 
      $("#stop").click(function(){
        clearInterval(timerID); // setInterval함수가 반환한 타이머 ID를 전달해야 하므로 addClock()이 아니라 timerID 변수를 사용한다.
        console.log("멈췄습니다.");
      });
 
    });
Math 클래스
실무에서 주로 사용되는 것 
Math.random() // 배너, 이미지 슬라이드의 컨텐츠를 랜덤하게 보여줄 때 . 컨텐츠의 위치를 무작위로 설정할 때
Math.ceil() // 게시판의 페이지 수를 구할 때
Math.sin() // 이미지 갤러리 제작 시, 이미지를 곡선을 따라 나열
프로퍼티 : PI(원주율 값)
함수(메서드) 목록... 주로 쓰이는 것만! 다른 자바스크립트 코어 클래스와는 달리 대부분의 기능이 클래스 메서드(정적메서드)로 구현되어 있어서 인스턴스 생성 없이 바로 사용할 수 있다.
abs() : 절대값을 반환
ceil() : 올림값을 반환
floor() : 숫자의 버림값을 반환
log(): 자연로그 값을 반환
max(): 두 수 중 큰 값을 반환
min() 두 수 중 작은 값을 반환
random() : 0과 1사이의 난수 값을 반환
round() : 가장 가까운 정수로 반올림하거나 반내림한 값을 반환
sqrt() 제곱근을 반환
String 클래스
문자열을 생성하는 기능을 시작으로 문자열과 관련된 유요한 기능이 있다. 
실무 활용
입력받은 아이디의 패스워드의 좌우 공백을 없애준다.
게시판 제작 시, 게시물의 특정 문자열을 다른 문자열로 치환 , 혹은 삭제가 가능하다.
`
주요 기능
프로퍼티 - length : 문자열 개수
함수(메서드) 목록(자주 쓰는 것만)
indexOf() : 스트링 인스턴스에서 특정 문자나 문자열이 처음으로 등장하는 위치의 인덱스를 반환함.
lastIndexOf() : 뒤에서부터  ''
charAt() : string 인스턴스에서 전달받은 인덱스에 위치한 문자를 반환한다.
slice()
split() : 
concat() :
toUpperCase() : 대문자 변환
toLowerCase() : 소문자 변환
replace() : 새 문자열 반환
등등..
핵심 내용
문자열 만들기
리터럴 방식 : var str = "hi";
string클래스의 객체를 생성해 이용 var str = new String("hi") ;
주의 사항 : 문자열 리터럴 방식 구문은  —--- 자바스크립트 해석 ----→ String클래스의 객체를 생성해서 이용하는 방식으로 변환되어 실행된다. 
alert("hi".length); //2
alert("hi".charAt(0)); //h
문자열 길이 알아내기 - length()

var str = "안녕하세요";
var len = str.length; //5
특정 위치의 문자 구하기 - charAt()

var str = "안녕하세요";
var ch = str.charAt(2); // 하
문자(열) 위치 찾기 indexOf()

var text =  "안녕하세요"
var ch = text.indexOf("하", 0);
특정 위치에 문자 추가

slice()
var result = 문자열.slice(start(문자열 시작 위치), end(문자열 끝 위치))
substr()

var result = 문자열.substr(start(문자열 시작 위치), length(문자열 개수))
특정 위치의 문자를 다른 문자로 변경하기  replace()

var result = 문자열.replace(searchValue(찾는 문자), newValue(대체 문자));
특정 위치에 문자 제거  slice()메서드와 substr()메서드를 이용하여 조합한다.
Data 클래스
날짜 및 시간과 관련된 유용한 기능
실무 활용
다이어리 - 달력, 현재 시간 출력, D-day, 플레이 경과 시
함수(메서드) 목록
getDate() 로컬 시간을 사용하여 일(월 기준) 반환
등등 엄청 많다.
0 (1월,일요일) 6(토요일), 11(12월)
Array 클래스 //배열 만들고 추가 삭제 찾기
리스트 출력
프로퍼티
length : 배열의 크기(개수)를 알 수 있다.
메서드 목록
concat(array)  두 개의 배열을 하나의 배열로 합친다.
push(data) 배열의 끝에 데이터를 추가 후 배열의 길이를 리턴한다.
pop() 배열의 마지막 항목을 제거하고 , 제거된 데이터를 반환한다.
shift() 배열의 첫 번째 데이터 제거 후 해당 값 리턴
unshift() 배열의 맨 앞에 데이터 추가 후 배열의 길이 반환
join() 지정한 구분자 이용 배열을 문자열로 변환 후 반환

a,b,c,d,e
arr.join(,);
abcde
splice ,slice, reverse, sort
실무에선 배열 리터럴 방식을 이용한다. js 에선 내부적으로 배열 클래스 방식으로 변환되어 실행된다.

1. 배열 리터럴 방식
var arr = ["num1", "num2", "num3"];
 
2. 배열 클래스 방식
var arr = new Array("num1", "num2", "num3");
배열 요소 개수 알아내기

var arr = ["num1", "num2", "num3"];
console.log(arr.length); // 3
특정 위치의 배열 요소 접근하기

var arr = ["num1", "num2", "num3"];
for(var i=0; i<arr.length; i++){      //i가 0이고, i<arr의 배열 수 일 때 까지 반복하고, i가 1씩 추가된다.
    var num = arr[i]                  // arr의 0번째 배열 요소 접근
    document.write(num + "<br />");
}
배열을 문자열로 만들기

var arr = 배열명.join([seperator]) // seperator 생략시 쉼표(,)가 구분자로 사용된다.
문자열을 배열로 만들기

var arr = 문자열.split(seperator)
특정 위치에 배열 요소 추가
push() 배열 마지막 위치에 배열 요소 추가

var result = 배열.push(element, [element]);
매개변수: 배열 마지막 위치에 추가할 배열 요소
리턴값 : 신규 배열 요소를 추가한 배열을 리턴
unShift() 배열 첫 번째 위치에 배열 요소 추가

var result = 배열.unShift(element, [element]);
매개변수: 배열 첫 번째 위치에 추가할 배열 요소
리턴값 : 신규 배열 요소를 추가한 배열을 리턴
splice() 배열 n번째 위치에 배열 요소 추가

var result = 배열.splice(start, deleteCount, [element]);
start: 추가 or 삭제할 배열 요소의 시작 위치
deleteCount: start부터 시작하여 삭제할 배열 요소의 개수(요소 추가시에는 0)
element: 추가 요소
리턴값: 삭제할 배열 요소를 추가한 배열을 리턴. (요소 추가시에는 X)
특정 위치의 배열 요소 삭제
shift() 첫 번째 요소 삭제

var result = 배열.shift();
매개변수: 없음
리턴값: 삭제된 배열 요소
pop() 마지막 요소 삭제하기

var result = 배열.pop();
매개변수: 없음
리턴값: 삭제된 배열 요소
splice() n번째 위치의 배열 요소 삭제

var result = 배열.splice(start, deleteCount, [element]);
start: 추가 or 삭제할 배열 요소의 시작 위치
deleteCount: start부터 시작하여 삭제할 배열 요소의 개수(요소 추가시에는 0)
element: 추가 요소
리턴값: 삭제할 배열 요소를 추가한 배열을 리턴. (요소 추가시에는 X)
배열 정렬하기
sort()

var result = 배열.sort([compareFunction]);
매개변수 : compareFunction은 정렬 순서를 정의하는 함수이다. 생략 시, 문자를 오름차순으로 정렬한다.
리턴값: 정렬이 완료된 결과값. 정렬에 사용된 원본도 변경된다.
문자 오름차순 정렬

배열.sort(function(a, b){
    return a - b; //음수 return
});
문자 내림차순 정렬

배열.sort(function(a, b){
    return b > a; 또는 b - a;
});
숫자 정렬하기

숫자도 문자열로 처리됨.


# 9장_ DOM

## 자바스크립트를 배운다는 것
1. 자바스크립트 core 문법: 기본 문법, 구조, 데이터 타입, 조건문, 반복문, 함수, 클래스
2. 자바스크립트 core라이브러리 : 자바스크립트에서 기본제공하는 타이머 함수, 문자열, 날짜 및 시간, 수학, 배열, 기타 전역함수
3. 자바스크립트 DOM : 노드, 스타일, 속성, 이벤트, 위치 및 크기 등을 다룰 수 있는 다양한 기능
4. 자바스크립트 BOM : 브라우저와 관련된 window, nav, loc, history, document, screen 객체들을 포함

## DOM
- 슬라이드 기능
- 아코디언 메뉴, hover 기능
- 서버에서 데이터를 받아 화면에 출력

## 노드
html 웹페이지 구성 요소의 가장 작은 단위
태그 뿐 아니라 텍스트 및 주석까지

### 핵심 DOM 객체
- 노드 : 노드를 다루는 기본 기능 ,프로퍼티 제공.
- document : 텍스트, 엘리먼트, 속성 노드를 생성
- element : html, xml 태그 요소의 기본 기능과 프로퍼티 제공.
- HTMLDocument  : document 객체를 확장하여 html용 프로퍼티, 메서드 추가한 객체. body가 바로 이 객체의 프로퍼티.
- HTMLElement : element 객체를 상속받은 html 태그 요소 전용 

## 노드 객체


# 10장_jquery

```<a href="api.jquery.com" target="_blank"></a>```
즐겨찾기 해두고 jqeury의 기능 익히기.

jquery는 DOM을 좀 더 쉽게 다룰 수 있게 만들어진 라이브러리 파일이다.
이 라이브러리는 자바스크립트의 prototype이라는 클래스 제작 문법으로 만들어졌다.
```$()```에서 jQuery의 인스턴스를 생성해준다. 

같은 선택자를 여러 번 호출할 일이 생길 경우,
변수로 정의해서 로직을 짠다.

```js
var $menu = $("#menu");
$menu.append..
$menu.append..
$menu.css...
```


# 11장_노드 찾기

## 노드 찾기
```js

$("#header") // 아이디로 찾기
$(".header") // 클래스로 찾기
$("h1") // 태그로 찾기
$("h1[class]") // class 속성을 들고 있는 h1 노드 찾기
$("input[type=text]") // text 타입의 input 노드 찾기
$("input[title^=V]") // input의 title 속성 값이 V로 시작하는 노드 찾기
$("input[title$=V]") // input의 title 속성 값이 V로 끝나는 노드 찾기
$("input[title*=V]") // input의 title 속성 값이 V를 포함하는 노드 찾기

```

## 찾은 노드 다루기

```js

.length // 객체 내부에 들어있는 노드 개수 구하기
.eq(index) // eq()메서드를 찾은 노드의 n번째 해당하는 노드 접근
.get(index) // 리턴값은 자바스크립트 DOM객체이다.
.each(function(index){// 대상에 들어있는 노드 개수만큼 매개변수 값으로 넘겨 받은 함수를 반복해서 호출한다.
  var $target = $(this);
  //또는
  var $target = $대상.eq(index)
});       


```
