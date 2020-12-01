# js_04_20201201
javascript_04_string 객체_



<!-- 
--------------------------
js_11.html
--------------------------
년월일시분초를 관리하는 [Date 객체]의 쓰임새를 공부한다.
-->
<!DOCTYPE html>
<html>
<meta charset="utf-8">
<head>

<style type="text/css">

  #xxx{
  font-family: tahoma, 굴림, 돋움, verdana;

  color: #444444;
    }
</style>

<title></title>

<script type="text/javascript">


  //*************************************
  // 한글 요일을 리턴하는 함수 선언 매개변수로 요일에 해당하는 번호 0-6(일-토)가 들어온다.
  //*************************************

        function getWeek1(weekNo){

          // 요일을 저장할 변수 선언하기
          var week = "";

          // 만약 매개변수 weekNo가 0이면 week 에 "일" 저장하기
          if(weekNo==0) {week = "일";}

          // 만약 매개변수 weekNo가 1이면 week 에 "월" 저장하기
          else if(weekNo==1){week = "월";}	

          // 만약 매개변수 weekNo가 2이면 week 에 "화" 저장하기
          else if(weekNo==2){week = "화";}	

          // 만약 매개변수 weekNo가 3이면 week 에 "수" 저장하기
          else if(weekNo==3){week = "수";}	

          // 만약 매개변수 weekNo가 4이면 week 에 "목" 저장하기
          else if(weekNo==4){week = "목";}	

          // 만약 매개변수 weekNo가 5이면 week 에 "금" 저장하기
          else if(weekNo==5){week = "금";}	

          // 만약 매개변수 weekNo가 6이면 week 에 "토" 저장하기
          else if(weekNo==6){week = "토";}	

          // week 변수 안의 데이터 리턴하기
          return week;

          //---------------------
          //위 코딩은 아래처럼 해도 된다.
          //---------------------
          //return["일","월","화","수","목","금","토"][weekNo];
        }




  //*************************************
  // 년 월 일 요일 오전 오후 시 분 초를 저장한 Array 객체를 리턴하는 함수 선언하기
  //*************************************
        
        
        function getDateArr(dateObj){
          // Date 객체의 메위주가 들어올 매개변수 선언하기


          // 년 월 일 요일 오전 오후 시 분 초를 저장할 Array 객체 생성하기
          var dateArr = [];

          //-----------------------

          // 오전 변수 저장한 amt 선언하기
          var amt = "오전";

          // 오후 변수 저장한 pmt 선언하기
          var pmt = "오후";

          // 오전 오후 담을 변수 저장한 am_pm 선언하기
          var am_pm = "";

          // 매개변수로 들어온 Date 객체에서 년도 구하기
          var year = today.getFullYear();

          // 매개변수로 들어온 Date 객체에서 월 구하기
          var month = today.getMonth()+1;

          // 매개변수로 들어온 Date 객체에서 일 구하기
          var date = today.getDate() ;

          // 매개변수로 들어온 Date 객체에서 요일 구하기
          var day = getWeek1(today.getDay());

          // 매개변수로 들어온 Date 객체에서 시간 구하기
          var hour = today.getHours();

          // 매개변수로 들어온 Date 객체에서 분 구하기
          var minutes = today.getMinutes();

          // 매개변수로 들어온 Date 객체에서 초 구하기
          var seconds = today.getSeconds();


          //-----------------------

          // 만약 hour 12 미만이면 am_pm변수 안의 오전(amt) 변수 저장하기
          // 그렇지 않으면  오후(pmt) 변수 저장하기
          if (hour<12){am_pm = amt;}else{am_pm = pmt;}

          // 만약 date가 10 미만이면 0 붙이기
          if (date <10){date = "0"+ date;}

          // 만약 month가 10 미만이면 0 붙이기
          if (month<10) {month = "0"+ month;}

          // 만약 hour 12 보다 크면 12 빼기
          if (hour>12) {hour = hour - 12;}

          // 만약 hour가 10 미만이면 0 붙이기
          if (hour<10) {hour = "0" + hour;}

          // 만약 minutes가 10 미만이면 0 붙이기
          if (minutes<10){minutes = "0"+minutes;}

          // 만약 seconds가 10 미만이면 0 붙이기
          if (seconds<10){seconds = "0"+seconds;}
          //-----------------------

          //Array 객체에 year 변수 안의 데이터 저장하기
          dateArr.push(year);

          //Array 객체에 month 변수 안의 데이터 저장하기
          dateArr.push(month);

          //Array 객체에 date 변수 안의 데이터 저장하기
          dateArr.push(date);

          //Array 객체에 day 변수 안의 데이터 저장하기
          dateArr.push(day);

          //Array 객체에 am_pm 변수 안의 데이터 저장하기
          dateArr.push(am_pm);

          //Array 객체에 hour 변수 안의 데이터 저장하기
          dateArr.push(hour);

          //Array 객체에 minutes 변수 안의 데이터 저장하기
          dateArr.push(minutes);

          //Array 객체에 seconds 변수 안의 데이터 저장하기
          dateArr.push(seconds);
          //-----------------------

          // Array 객체의 메위주 리턴하기
          return dateArr;		
        }





  //*************************************
  // 두 날짜의 차이를 일수로 구해 리턴하는 함수 선언하기
  ///*************************************

        function getIntervalDate(
            dateObj1	//Date 객체의 메위주가 들어올 매개변수 선언하기
            , dateObj2	// Date 객체의 메위주가 들어올 매개변수 선언하기
          ){

          //1970.1.1 부터 dateObj1에 저장된 Date 객체의 날짜까지의 초 구하기
          var second1 = dateObj1.getTime();

          //1970.1.1 부터 dateObj2에 저장된 Date 객체의 날짜까지의 초 구하기
          var second2 = dateObj2.getTime();

          // 구한 2개의 초를 빼기
          var second3 = (second2 - second1)/1000;

          // 구한 초를 일로 바꾸기
          var date = second3/(60*60*24)

          // 구한 일이 0 미만이면 -1 곱해서 양의 숫자로 만들기
          if(date<0){
            date = date*-1;
          }

          // 구한 일을 리턴하기
          return date;

        }



      </script>
    </head>
    <body id = "xxx" >

      <script type="text/javascript">
        //--------------------------------------
        // 현재 세스템 날짜를 관리하는 [Date 객체] 생성하기
        // 현재 시스템 날짜는 흘러가는 현재 시간을 의미한다.
        //--------------------------------------
          // [Date 객체] 생성 방법
          // 		=> var 변수명 = new Date(년, 월, 일, 시, 분, 초);
          //--------------------------------------
          // <주의> 현재 시스템 날짜를 관리하는 [Date 객체] 생성 시엔 아래처럼 한다.
          //		=> var 변수명 = new Date();
          //--------------------------------------

        var today = new Date();


        //--------------------------------------
        // 1989년 10월 2일 날짜를 관리하는 [Date 객체] 생성하기
        // Date 객체는 월을 0-11 로 관리하므로 월은 -1 하고 입력한다.****
        //--------------------------------------
        var birth = new Date(1990,1,3);

        //---------------------
        // 현재 년월일시분초 입력하기
        //---------------------
        document.write("현재시간 => " 
          + today.getFullYear() + "년 "
          + (today.getMonth()+1) + "월 "
          + today.getDate() + "일 "



          + getWeek1(today.getDay()) + "요일 "


          + today.getHours() + "시 "
          + today.getMinutes() + "분 "
          + today.getSeconds() + "초" 
          + "<hr>"
          );
        //0부터 6까지 숫자를 월~금으로 만들어야한다
        // 이걸 함수로 만들어서 사용.
        // getFullYear() => Date 객체가 갖고있는 연도를 갖고있는 메소드
        // 월 뽑은 후에 +1을 꼭 해줘야 인간이 아는 월이 나온다.****


        //---------------------
        // 1990년 02월 03일 날짜의 년월일시분초 출력하기
        //---------------------
        document.write("내 생일 => " 
          + birth.getFullYear() + "년 "
          + (birth.getMonth()+1) + "월 "
          + birth.getDate() + "일 "


          //-----------------
          // 요일을 숫자->한글로 변경하는 함수 getWeek1()
          //-----------------
          + getWeek1(birth.getDay()) + "요일 "


          + birth.getHours() + "시 "
          + birth.getMinutes() + "분 "
          + birth.getSeconds() + "초" 
          + "<hr>"
          );

        //-----------------
        // 1992년 5월 8일 날짜에 태어난 사람의
        // 100일 잔치 날짜는 언제인지 출력하기
        //-----------------
        //----------------------------------
        // 1992년 5월 8일 날짜를 관리하는 [Date 객체] 생성하기
        //----------------------------------
        var kimran_birthday = new Date( 1992, 4, 8+100 );
        document.write( "김란 돌 잔치날 =>"+ kimran_birthday.getFullYear() + "년 "
          + (kimran_birthday.getMonth()+1) + "월 "
          + kimran_birthday.getDate() + "일 "+ getWeek1(kimran_birthday.getDay()) + "요일 "+"<hr>")



        //----------------------------------
        // 최승환 2020년 11월 11일 여자친구를 사귀었다.
        // 만난 100일 기념일은 언제인가?
        //----------------------------------
        var choi_meetingday = new Date(2020, 10, 11);


        choi_meetingday.setDate(choi_meetingday.getDate()+100);

        document.write("최승환 100일 날=>"+choi_meetingday.getFullYear() + "년 "+ (choi_meetingday.getMonth()+1) + "월 "+ choi_meetingday.getDate() + "일 "+ getWeek1(choi_meetingday.getDay()) + "요일 "+"<hr>");



        //----------------------------------
        // 현재 오늘 태어난 아기의 100일 잔치 날짜는 언제인지 출력하기
        //----------------------------------
        var aga_birth = new Date();

        aga_birth.setDate(aga_birth.getDate()+100);

        document.write("현재 오늘 태어난 아기 100일 잔치 날짜=>"+aga_birth.getFullYear() + "년 "+ (aga_birth.getMonth()+1) + "월 "+ aga_birth.getDate() + "일 "+ getWeek1(aga_birth.getDay()) + "요일 "+"<hr>");



        //----------------------------------
        // 2025년 2월의 마지막 날짜는 며칠인지 출력하기
        //----------------------------------
        var finalday_2month_2025 = new Date( 2025 , 2 , 1-1);

        document.write("2025년 2월의 마지막 날짜=>"+finalday_2month_2025.getFullYear() + "년 "+ (finalday_2month_2025.getMonth()+1) + "월 "+ finalday_2month_2025.getDate() + "일 "+ getWeek1(finalday_2month_2025.getDay()) + "요일 ");

        //----------------------------------
        // 나는 몇일을 살았나
        // [1989년 10월 2일] ~ [오늘] 까지 몇일이 흘렀는지 일수 알아내기
        //----------------------------------

        //1989.10.2을 관리하는 Date객체 생성하기
        var hwang_birth = new Date(1989,9,2);

        // 오늘을 관리하는 Date 객체 생성하기
        var today = new Date();

        // 1970.1.1 ~ 1989.10.2일 사이의 초를 구하기
        var second1 = hwang_birth.getTime();

        // 1970.1.1 ~ 오늘 사이의 초를 구하기******
        //getTime메소드( 항상 x1000 이 곱해져 있다.)
        var second2 = today.getTime();

        var second3 = (second2 - second1)/1000;

        document.write("황보민씨가 산 초 =>"+second3+"<hr>");



        var date = second3/(60*60*24);

        document.write("황보민씨가 산 일수 =>"+date+"<hr>");



        //----------------------------------
        // [오늘] 날짜를 아래 형식으로 출력하기 
        // xxxx년 xx월 xx일 x요일 오전 또는 오후 xx시 xx분 xx초
        // <주의> xx시는 00~12 사이 이다.
        // <주의> xx분은 00~59 사이 이다.
        // <주의> xx초는 00~59 사이 이다.
        //----------------------------------
        // <예> 2020년 12월 01일 화요일 오후 04시 01분 13초
        //----------------------------------

        var today = new Date();

        var amt = "오전";
        var pmt = "오후";


        var year = today.getFullYear();
        var month = today.getMonth()+1;
        var date = today.getDate() ;
        var day = getWeek1(today.getDay());
        var hour = today.getHours();
        var minutes = today.getMinutes();
        var seconds = today.getSeconds();

        var am_pm = "";

        if (hour<12){am_pm = amt;}else{am_pm = pmt;}
        if (date <10){date = "0"+ date;}
        if (month<10) {month = "0"+ month;}
        if (hour>12) {hour = hour - 12;}
        if (hour<10) {hour = "0" + hour;}
        if (minutes<10){minutes = "0"+minutes;}
        if (seconds<10){seconds = "0"+seconds;}


        document.write(
          "현재시간 => "
          + year + "년 "
          + month + "월 "
          + date + "일 "
          + day + "요일 "
          + am_pm + " "
          + hour + "시 "
          + minutes + "분 "
          + seconds + "초"
          +"<hr>"
        );
        //------------------------------
        // getDateArr 함수 호출하여 년 월 일 요일 오전오후 시 분 초 를 저장한
        // Array 객체 메위주 구하기
        //------------------------------
        var dateArr = getDateArr(today);

        //------------------------------
        // Array 객체 안의 배열변수 데이터 출력하기
        //------------------------------
        document.write(

          "현재시간 => "
          + dateArr[0] + "년 "
          + dateArr[1] + "월 "
          + dateArr[2] + "일 "
          + dateArr[3] + "요일 "
          + dateArr[4] + " "
          + dateArr[5] + "시 "
          + dateArr[6] + "분 "
          + dateArr[7] + "초"
          +"<hr>"

          );		

      </script>

    </body>
    </html>
