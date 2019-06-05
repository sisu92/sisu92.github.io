# Form 100% 개발자가 처리해야 하는 것
다음,네이버 개발자 등록?
~~~java
<select name="play" size="8"> //-> Select에 사이즈를 주면 셀렉트 아니면 콤보박스
------------------------------------------------------------

window.onload= function() {
	var up=document.getElementById('up');
	var down=document.getElementById('down');
	document.getElementById('up').onclick=function () {
		var idx=document.frm.play.selectedIndex;
		var optsel=document.frm.play.options;
		var str=optsel[idx].value;  //text도 가능함
		alert(str);
	}
~~~



~~~java
window.onload=function ( ) {
	document.myForm.txt0.value='HaHa';
	document.myForm['txt1'].value='HoHo';
	
	document.getElementById('btn').onclick=function() {
		for(var i=0;i<4;i++)
			{
			document.myForm['txt'+i].value='Data'; //-> 이런방식으로 반복가능
			}
		
	}

-------------------------분석해라 ---------------------
	frm.onsubmit=function(e) {
			e.preventDefault();  //고유의 기능을 막는다. 
            e.stopPropagation(); //->이런 경우도 있다. 
			var agree = frm.sss;
			if(! sss.checked) {
				alert('Please check!!!!');
				return;
			}
			frm.submit();
		}
---------------------------------------------

//1. 아이디로 얻어괴
	//var name=document.getElementById('name');
//	var name=document.querySelector('#name');
	//	result.innerHTML= name.value;
		
		//2. 클래스 이름으로 얻어오기
		//var name=document.getElementsByClassName('cname');
		var name=document.querySelectorAll('.cname');
		result.innerHTML= name[0].value;
		
	
		//3. tag name으로도 가능
	//	var name=docoment.getElementsByTagName('input');
	//	result.innerHTML= name[0].value;
		//4. 폼으로 얻어오기
	//	var document.fm.name;
	//	result.innerHTML = name.value;
~~~

##퀴러스트링 - NAME을 줘야지 url을 타고 넣어간다.
### http://koxo.com/lang/js/ ->사이트 참조;
# DOM ( + BOM )