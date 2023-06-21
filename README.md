# number baseball game

## **** 숫자로 하는 야구 게임 ****
 
- 숫자는 1~9까지로 제한
- 서로 다른 숫자 3개로 이루어진 두 개의 배열(com[], usr[])을 비교하여 볼카운트 계산
   **컴퓨터가 내는 숫자는  => 입력받는 인수 VS 컴퓨터가 발생시키는 난수
- 컴퓨터가 내는 숫자 3개의 배열 ==? 사용자가 내는 숫자 3개의 배열
  : 숫자와 배열의 자릿수가 일치할 때는 strike!
   : 숫자는 일치하지만 자릿수가 틀릴 때는 ball!
  ex) 컴퓨터 내는 숫자가 [3][6][9], 사용자가 내는 숫자가 [6][3][9] 이면 strike : 1 & ball:2

- 숫자 야구 게임은 main(), 두 개의 playGame() 로 구성 => 메소드 오버로딩
ex) add(int x, int y){....}
    add(double x, double y){....}
    add(){.....}
- playGame() : 3개의 정수를 인수(매개변수 값)로 받는 것 vs 인수가 없는 것
- 프로그램 실행 시, 컴퓨터가 내는 숫자에 인수를 입력하면 인수가 필요한 playGame(,,)이 호출
 인수를 입력하지 않으면 컴퓨터가 인수 없는  playGame() 호출하고 난수를 발생시켜 숫자 세 개를 얻는다.

- 사용자가 입력하는 세개의 숫자데이터는 정수로 형 변환 필요
- playGame()는 컴퓨터가 내는 3개의 숫자와 사용자가 입력한 숫자데이터를 비교하여 볼카운트를 진행
- 사용자가 진행한 결과를 매번 화면 출력
- 총 11번의 기회를 제공하며, 3strike 일 경우 게임 종료. 볼카운트를 이용하여 사용자가 숫자를 추측한다.
- main()에서는 메소드의 반환값을 저장할 result 변수 생성
- 세 숫자를 외부에서 입력받아 정수형으로 변환시켜 plamyGame(,,)에 인수를 넣어 호출 후 반환값 result에 저장
 (입력이 불완전하면 playGame()을 호출)
-   2회 이하 시도 : 참 잘했어요
    5회 이하 시도 : 잘했어요
    9회 이하 시도 : 보통이에요
    10회이상 : 분발하세요
## **해결해야할 문제1) 서로 다른 세 개의 정수를 1~9까지 Random()를 이용하여 난수발생시키시오.
## -> 1~9까지 Random()를 이용하여 난수발생 구현
## int x, y, z; //컴퓨터가 선택하는 3개 숫자
## Random r= new Random(); //난수발생 Random()메소드로 객체변수 r 생성
## x= Math.abs(r.nextInt() % 9) + 1; // 1~9 사이의 난수 발생
## //y= Math.abs(r.nextInt() % 9) + 1;
## //z= Math.abs(r.nextInt() % 9) + 1;
## ->서로 다른 세 개의 정수를 만드는 코드 구현
## do{
 ## y= Math.abs(r.nextInt() % 9) + 1;
 ## }while(y==x); // 만일 난수 y가 x와 같은 수일 때 다시 한 번 난수 발생 반복
## do{
## z= Math.abs(r.nextInt() % 9) + 1;
## }while((z==x)||(z==y)); // 만일 난수 y가 x 혹은 y와 같은 수일 때 다시 한 번 난수 발생 반
## **결론 : x, y, z는 서로 다른 1~9까지의 정수로 만들어짐
## - do-while문
## do {
## 명령문;
## } while(조건문);  //먼저 명령문을 실행한 후, 조건이 true인 경우에는 명령문을 반복, 조건이 false가 되면 종료
## **해결해야할 문제 2) 3개의 인수를 받는 playGame(,,)에서 주어진 세 개의 숫자를 com 배열에 저장하고,
## 사용자가 게임에 사용할 숫자 세 개는 usr배열에 저장한다.
## 이때 사람이 입력하는 값이 0, 9보다 큰 숫자, 같은 숫자를 입력하지 않도록 do-while문의 조건문을 작성하시오.
## do {  
## // 키보드로부터 3개 숫자 입력받아 usr[0],usr[1],usr[2] 에 저장
## } while( (usr[0]==0)||(usr[1]==0)||(usr[2]==0) ||    //사람이 입력하는 값이 0
## (usr[0]>9) ||(usr[1]>9) ||(usr[2]>9)  ||    //사람이 입력하는 값이 9보다 큰 숫자
## (usr[0]==usr[1])||(usr[1]==usr[2])||(usr[0]==usr[2]) // 서로 같은 숫자를 입력    
## );
## - 1. *1~9까지 Random()를 이용하여 난수발생 구현(int x, y, z; 컴퓨터가 선택하는 3개 숫자)*
![asd](https://github.com/whasdnck/numberGame/assets/127116197/46e5aa14-4f00-4268-b0b8-b159b66ef8d0)
![dd](https://github.com/whasdnck/numberGame/assets/127116197/d25656cf-46f0-4cc1-9215-06de8692e01c)
## - 2. *while(3strike or 시도횟수가 11번 초과로 종료전까지)*
![qq](https://github.com/whasdnck/numberGame/assets/127116197/ec9b86a7-8d33-46a7-bbfd-b06c902b83ee)
## - 3. *볼카운트 계산 하기*
![화면 캡처 2023-06-20 140707](https://github.com/whasdnck/numberGame/assets/127116197/1b660134-bd1f-46ff-b36b-5fb5266943fa)
## - 4. *진행자가 게임실행시 외부에서 직접 인수를 입력하여 com배열에 저장 한다.*
## - 5. *main mathod 사용하기*
![화면 캡처 2023-06-20 141602](https://github.com/whasdnck/numberGame/assets/127116197/7684e01e-c5b3-4475-99f7-24f511013413)

# - 실행문.
## 시도 2번 이하
![화면 캡처 2023-06-21 135929](https://github.com/whasdnck/numberGame/assets/127116197/66e49312-99cc-4714-9d59-1e67d3ba2895)
## 시도 3번 부터 5번 이하
![화면 캡처 2023-06-21 140103](https://github.com/whasdnck/numberGame/assets/127116197/33f45885-10fc-48bb-bfa4-c2eabdbff6a1)
## 시도 6번~9번 
![화면 캡처 2023-06-21 140259](https://github.com/whasdnck/numberGame/assets/127116197/cd6c9970-7933-447e-b1f9-31e316bb9bf8)
## 시도 10번
![화면 캡처 2023-06-21 140634](https://github.com/whasdnck/numberGame/assets/127116197/80e6a09b-4914-4ed3-9f97-f4e86132d69f)

