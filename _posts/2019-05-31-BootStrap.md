#오늘의 수업 
##1. BootStrap
~~~html
http://bootstrapk.com/ 부트스트랩 한글판
  - css,js 파일들 다운받아서 쓰거나 : 개발자 입장, [ 인터넷이 없는곳에서 개발할 수 있기 떄문에 ]
  - 웹사이트에 있는 코드를 가져다 쓴다.

-> 시작하기 -> 기본 템플릿 COPY
->css/css.min 동일한 거 min이 배포용
< nav> 영역 복사 붙이기;  container -> 붙이기   cutsom 긁어오기 
custom/starter-template.css -> 파일만들기;
그리구 각각맞게 꾸미기 
필요한 소스를 컴포넌트에 찾구, 소스 카피해서 BODY안에 넣기;
※주의  ->  브라우저 지원여부 확인
       -> 서드파티 지원여부 확인 [ 부트스트랩, 구글맵 출동? ]

       크롬->material-kit ->https://www.creative-tim.com/

       btn -> btn btn-default,btn-primary,btn-success
       모바일일 경우 -> 이미지보다 이런식으로 작업해줘야한다.
       속도, 무거우지니깐;
       label label-primary // alert alert-warning
       //btn-block btn btn-primary btn-sm

     table 속성
       table-bordered table-striped table-hover
--------------
//hover form
.table tr:nth-child(even) { background: orange; }
.table tr:hover{ background:lime;}
-------------------
<div class='col-md-2'>  ->  col-md-push-10' 서로
<div class='col-md-10'> -> col-md-pull-2'  바꿀때 
glyphicon glyphicon-info-sign 이미지 대신 사용한다.

<li class='active'><a href="#home" data-toggle="tab">독도<a></li>
 <div class='tab-pane active'id="home">




 bxSlider, 캐러셀 슬라이드(부트스트랩) 설정!!!
 <div id="carousel-example-generic"class='carousel slide' >
            <!-- Indicators -->
            <ol class='carousel-indicators'>
              <li data-target="#carousel-example-generic" data-slide-to="0" class="active"></li>
              <li data-target="#carousel-example-generic" data-slide-to="1"></li>
              <li data-target="#carousel-example-generic" data-slide-to="2"></li>
            </ol>
             
             <!-- Carousel items -->
             <div class='carousel-inner'>
                <div class="item active">
                   <img src="./images/slide1.jpg" alt="First slide">
                </div>
                <div class="item">
                   <img src="./images/slide2.jpg" alt="Second slide">               
                </div>
                <div class="item">
                   <img src="./images/slide3.jpg" alt="Third slide">                 
                </div>
             </div>

         <ul class='nav navbar-nav'>
          <li class='dropdown'>
            <a class='dropdown-toggle'href="#" data-toggle="dropdown">메뉴 1 <b class="caret"></b></a>
            <ul class='dropdown-menu'>
~~~
##2. 화면 만들기
### 이제는 개발자 UI도 직접 만들어야한다. 반응형;
### 첫화면만 받구, 나머지는 개발자가 직접 수정;, 미적감각이 있어야 한다.

##3. 자바로 웹페이지 내용(웹데이터)  끌어오기?! [구경]
~~~JAVA
package crowling;

import java.io.IOException;

import org.jsoup.Jsoup;
import org.jsoup.nodes.Document;
import org.jsoup.nodes.Element;
import org.jsoup.select.Elements;

public class Hanbit {

	public static void main(String[] args) {
		
		
		try {
			String url="http://www.hanbit.co.kr/media/";
			Document doc = Jsoup.connect(url).get();
			//System.out.println(doc);
			Elements body=doc.select("div.sub_book_list_area  .book_tit > a");
			for(Element title :body) {
				System.out.println(title.text());
			}
		//	System.out.println(body);
		} catch (IOException e) {
			System.out.println("Exception!!!!");
			e.printStackTrace();
		}

	}

}

~~~