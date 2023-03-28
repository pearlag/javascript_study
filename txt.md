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














