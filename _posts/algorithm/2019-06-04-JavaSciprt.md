#자바스크립트 활용하기 
##검색해서 활용하기;
##아이디어 ㅎㅎ->기존의 자바개념을 바탕으로
~~~java
//메뉴판 -> ETC 
var td=document.getElementsByClassName('menu');
	alert(td.length);
	for(var i=0; i<td.length; i++)
		{
		
		td[i].onclick = function() {
			//alert(i);
			alert(this.childNodes[0].nodeValue+this.childNodes[2].nodeValue);
		}
 		}

//2.JS에서 요소 찾아서 이벤트 함수 연결
	window.onload=function() {
		alert('This Page is close move to playdata');
		window.location.href='http://playdata.io'; //지정된 경로로 이동
        location.href='http://playdata.io'; // 동일한 결과
        window.location='http://playdata.io';// 동일한 결과
~~~
##1. 윈도우 객체 활용

~~~java
<script type="text/javascript">

	window.onload = function() {
		// 그 값을 가지고 와서
        var sel=document.frm.chooseSite;
		sel.onchange=function showSite()
		{
			//페이지 변환
            window.location=sel.value;
            //페이지 변환, 뒤로가기 금지
            location.replace(sel.value);
		};
		
	}
	
</script>  //-> 이벤트 처리2번 후, 그 값을 가지고 와서 페이지 변환

<script type="text/javascript">

	window.onload = function() {
		var sel=document.frm.chooseSite;
		sel.onchange=function showSite()
		{
			setTimeout(function  ( ){
				window.location=sel.value; //2초후 화면전환, 축약형 
                //눈에 익혀두기
			},2000);
		};
		
	}
	
</script>

[예] 인덱스 값이 1이라면 http://www.daum.net으로 창을 연다  
		var idx=sel.selectedIndex;
		if(idx==1) winObj.location.href='http://www.daum.net';
		else if(idx==2) winObj.location.href ='http://www.naver.com';

        //===>>>switch문 변경 가능 Break; 잃지 말구
~~~


<script type="text/javascript">
		//3_2_window_opened.html 창을 열기
		var winObj = window.open('3_2_window_opened.html','','width=400,height=380');
		winObj.focus();
		//열은곳!!!!
	</script>   

<script type="text/javascript">
window.onload = function() {
	var sel=document.frm.site;
	for(var i=0; i<sel.length;i++)
		{
		sel[i].onclick=chageSite;
		}
	function chageSite() {
	switch(sel.value) {
	case '0': opener.location.href='http://www.daum.net';break;
	case '1': opener.location='http://www.naver.com';break;
	case '2': opener.location.href='http://www.nate.com';break;
	
	}
    	window.close();// 현재 창 닫기;
	}
}
			
	//열린 곳!!!!!->연 곳으로 갈려면 'opener'
</script>

-----------------------------------이해
<script>
window.onload 
winObj.frm1.choose1.value = document.frm.

<script type="text/javascript">
	function sel(){
		parent.frm.result.value=document.fm.gender.value;
	}
</script>
<title></title>
</head>
<body>

<form name='fm'>
	받은 결과 : <input type='text' name='result' size='20'/><hr/>
	<input type='radio' name='gender' value='남자'  onclick='sel()'>남자
	<input type='radio' name='gender' value='여자' onclick='sel()'>여자
</form>
</body>

-----------------------------------------


##2. Forms 객체 활용
~~~java


~~~