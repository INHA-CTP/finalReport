<div style = 'height:850px;'>
    <div style = 'margin:20px; text-align:center;'>
        <div style = 'margin-top:130px; font-size:50px;'>
            <p>종합설계 최종 보고서</p><p style = 'font-size:30px;'>(강의추천 기반 시간표 웹)</p>
            <img src = 'SymbolMark.jpg' height="200" style = 'margin:0 auto;'/>
        </div>
        <div style = font-size:15px;text-align:right;margin-top:340px;'>
            <p><strong>강추조</strong><br/>12114497 한정(hanjungv@gmail.com)<br/>12142380 이강호(cannalee90@gmail.com)</p>
        </div>
    </div>
</div>
<center><h1>종합설계 최종보고서</h1></center>
<div style = "text-align:right; font-size: 13px;margin-bottom:40px;">강추 조 : 한정(컴공, 12114497), 이강호(컴공, 12142380)</div>

### 주제 정의
<h5>최종목표 : **다양한 사용자 환경을 만족시키는 시간표 웹 제작 및 사용자 맞춤 수업 추천 시스템 구축**</h5>
* 시간표를 웹, 모바일 웹 모두에서 쉽게 작성할 수 있게 도와준다.
* 추천을 하는 것 : 교수님의 특정강의
    * 개인의 평가를 받아 이 평가를 기반으로 추천을 해주게 됩니다.
    * 평가 점수를 예측하고 개인과 유사한 집단을 찾아 개인의 점수를 예측합니다.
    * 여러 알고리즘을 적용해 보고 MAE(Mean Absolute Error)를 기준으로 추천 방식을 지속적으로 개선합니다.
        * 데이터의 특성에 따라 여러가지 알고리즘을 선택해 보고 더 나아가 저희만에 추천 알고리즘을 만드는 것을 목표로 하고 있습니다.
        * MAE : 예측 점수와 실제 점수의 차이를 측정하여 평균을 낸다. 이를 통해 해당 알고리즘의 정확성과 가중치를 판단 할 수 있습니다.
    * 이를 통해 추천의 만족도를 높일 수 있을 것입니다.

### 배경
과거 20%의 주 품목들이 전체 매출의 80%를 차지하였다. 그러나 점차 개인 성향이 중시되며, 인터넷의 성장으로 정보의 접근이 쉬워지자 나머지 80%의 비주류 품목의 전체 매출이 무시 못할 규모가 되었다. 최근 IT 기업들은 이러한 현상 주목하고 개인 성향을 중시한 추천 알고리즘으로 시스템을 구축하기 시작하였고, 그 결과 매출 및 점유율 괄목할만한 결과를 얻어내었다. 추천 시스템의 등장은 시장의 패러다임과 라이프 스타일을 바꾸는 등 사회 전반에 영향을 미치고 있다. 이에 평소 알고리즘에 관심이 많았던 캡짱스톤조는 추천 알고리즘을 실제 적용하고 이해해보고자 추천 시스템을 구현하려고 한다.

- 목표 및 기대효과
    * 간편한 UI/UX 제공으로 쉬운 시간표 제작
    * 강의 몰림현상을 줄임
    * 좋은 강의들의 인원 부족으로 인한 강의의 폐강을 줄임
    * 학생들의 성향 파악을 통한 추천으로 만족도를 높이고 수강 포기 확률 감소
    * 정보의 불균형을 해소를 통한 수업 만족도 증가
- 관련 분야 survey
    * Stanford Jeffrey D. Ullman *mining massive datasets* 강의 수업자료
        * 기본적인 Recommend System 개념 학습
        * 신뢰도 계산법 및 적절한 선택법 학습
    * 카이스트 제 8회 ROSAEC 워크샵자료 *Recommendation System* "협업 필터링을 중심으로"
    * Guide to Datamining(http://guidetodatamining.com/)
        * 기본적인 Recommendation System 개념 학습
        * python을 통한 코딩 실습
    * mahout을 이용한 recommendation system Overview
        * recommendation system library 확인
    * `python` 과 `mysql` linking, 기존에 가지고 있던 데이터 마이닝 연습
        * `python`으로 `mysql`에 있는 데이터 변경 후 원래 서버와 linking하여 저장
    * `mongoDB`에 저장된 데이터를 Python을 통해 `mysql` 저장
    * AWS SQS(https://goo.gl/oDsxv2)
        * 데이터에 동시에 접근하여 문제가 발생하는 것을 해결하기 위해 `AWS SQS`사용 필요
    * MAE(https://goo.gl/564uoH)
        * 해당 데이터에 대한 당위성, 평가법 조사


- 유사 프로젝트 검색 및 해당 프로젝트 결과물들의 문제점
    -  [인하대학교 수강신청, http://sugang.inha.ac.kr/sugang/](http://sugang.inha.ac.kr/sugang/) : 학교 수강신청 사이트
        * 강의 선택이 한 화면에서 이뤄지지 않음
        * 모바일에 최적화 되어있지 않음<br/>
        <img src = '/img/com1.png' height="450"/>
        <img src = '/img/com2.png' height="350"/>
        * 컴퓨터 에서 본 화면입니다.<br/>
        <img src = '/img/phone1.png' height="400"/>
        <img src = '/img/phone2.png' height="400"/>
        * 모바일에서 본 화면입니다.<br/>

    - [에브리타임, http://everytime.kr/](http://everytime.kr/) : 시간표 제작 및 익명 커뮤니티
        * 추천 시스템 부재
        * 실제 시간표가 수강신청 사이트에 등재 된 후 약 1주일 후 반영<br/>
        <img src = '/img/com3.png' height="300"/>
        <img src = '/img/com4.png' height="300"/>
        * 컴퓨터 에서 본 화면입니다.<br/>
        <img src = '/img/phone3.png' height="350"/>
        * 모바일에서 본 화면입니다.<br/>

    - [SNUTT, http://snutt.kr/](http://snutt.kr/) : 서울대학교 시간표 제작
        * UI/UX 디자인 부재
        * 서울대 자대에만 사용되는 시스템
        * 추천 시스템 부재<br/>
        <img src = '/img/com5.png' height="350"/>
        * 컴퓨터에서 본 화면입니다.<br/>
        <img src = '/img/phone4.png' height="350"/><br/>
        * 모바일에서 본 화면입니다.

    - [주관식 강의백서,https://goo.gl/PKoyQc](https://goo.gl/PKoyQc) : 인하대학교 주관식 강의백서
        * 불편한 UI/UX
        * 어려운 검색, 강의에 대한 자료의 낮은 가독성
        * 모바일 최적화 부재
        * 단순한 엑셀자료, 데이터 부족<br/>
        <img src = '/img/com6.png' height="440"/><br/>

    - 기존 프로젝트와 제안 내용과의 차이 및 기존 문제 해결 방안
        * 추천 시스템
        * 사용이 간편한 UI/UX
        * 웹을 통해 여러 디바이스 환경을 만족시켜야 합니다.

### 개발 내용
- 개발 플랫폼 : **Web** <br/>
    1. 높은 호환성(OS에 국한되지 않음)<br/>
    2. 자바스크립트 기반의 높은 확장성<br/>
    3. 상대적으로 많은 라이브러리와 자료 존재<br/>
    4. 서버 언어로 `Node.js`를 사용하여 런닝 커브를 최소화<br/>

- 상세 요구사항
    * 기능적 요구사항 (functional requirements)
        * 과목 recommendation systems
        * 시간표 제작
        * 모바일 환경을 고려한 반응형 웹
        * 기존보다 쉽고 간편한 검색
    * 비기능적 요구사항 (non-functional requirements)
        * 해당 과목에 관심이 있는 인원 명시를 통한 경쟁 가능성 제시로 수강 인원 분산 유도
        * 추천 시스템 사용 유도
        * 플로우차트(다음페이지 상세)
        <img src = '/img/flowchart.png' height = 1030/>

### 개발 방법
- 개발 일정 및 팀원간 역할 분담
    - Recommendation part(한정)
    - Application part(이강호)
    <img src = '/img/gantt.png' height = 1030/>

- Web Application 개발을 위한 Open Source
  - React
      - facebook에서 만든 유저인터페이스 라이브러리
      - 페이스북, 인스타그램, 넷플릭스와 같은 웹 기반의 서비스에서 가장 널리 쓰고 있는 자바스크립트 프레임워크
      - 향후 모바일 앱을 만들때도 `React-native`를 사용해서 쉽게 포팅이 가능하다.
      - UI를 component를 통해서 UI의 재사용이 쉬워진다.
      - VIRTUAL DOM이라는 개념을 사용해서 상태의 변경에 반응하여 UI가 자동으로 변화되는 것이 특징
  - Babel
      - `ES6`와 `ES7` 모든 웹 브라우저에서 호환 가능하도록 변환해주는 transcompiler
  - Redux
      - 페이스북이 제시한 새로운 `Flux` 아키텍처의 구현체
      - `React`로 이루어진 앱에서 효율적인 데이터 흐름을 위해 사용하는 라이브러리
      - `Eco-system`이 성공적으로 유지되고 있어서 많은 사람들이 `Redux`기반의 라이브러리를 만들어내고 있다.
  - Node.js
      - `Javascript` 다양한 환경에서 사용할 수 있는 런타임 환경으로써, Non-blocking I/O와 단일 스레드 이벤트 루프를 통한 높은 처리 성능이 특징. 브라우저 기반의 자바스크립트를 확장
      - `Javascript` 기반이기 때문에, 상대적으로 프론트앤드와 같이 준비하기에는 런닝 커브가 낮다.
      - 내부 웹서버의 성능이 좋아서 상대적으로 배포가 쉽다.
  - express
      - `Node.js`에서 가장 많이 쓰이는 웹 프레임워크
  - passport
      - `Node.js`에서 가장 많이 쓰이는 유저 인증을 위한 미들웨어
  - SASS
      - `CSS`를 확장하는 pre-processor
  - webpack
      - `Javascript`와 각종 정적파일의 모듈화와 개발 서버를 제공해주는 라이브러리      
  - mysql
      - 가장 널리 쓰이고 있는 오픈소스 RDBMS
  - redis
      - 메모리 기반의 key/value NoSQL DBMS
  - lodash
      - 자바스크립트 기능 확장 라이브러리
  - beautifulsoup4
      - 파이썬기반의 html 파싱 라이브러리
- 추천 : **특정 교수님의 강의를 추천해줍니다.**
    * 사용하는 방식 : **Collaborative filtering**
        * 사용자의 평가 내용을 이용합니다.
        * 과거 입력해 놓은 아이템을 기반으로 미래 아이템을 예측합니다.
        * 데이터가 많아질 수록 높은 만족도를 나타낸다.
        * 데이터가 적을 경우 Cold start가 있습니다.
        * Collaborative filtering을 선택한 이유
            1. Content-based에서 추천해줄 Item을 어떻게 모델링 하느냐에 따라 추천의 질이 크게 달라 지는데 개인의 임의대로 카테고리를 나눠 분석하는 것이 만족성이 높은 추천을 하기 어려울 것 이라 생각했습니다.
            2. 4학년 학생이 들은 과목은 많아야 35~40개 내외. 많아야 40개의 점수를 사용자들이 입력하는데 크게 어려움이 없을 것이라 예상했습니다.
            3. 졸업자들의 데이터가 강력하게 사용 될 수 있을 것이라 생각했습니다.(빠른수집또한 가능할 것이라 생각)
            3. Content-based를 사용했을 때 결과 예측이 쉬웠다. 실제로 이 프로그램을 사용했을 때 만족도 있는 추천을 할 지 궁금했습니다.
        * 유사도 측정
            1. Cosine-similarity : 가장 많이 사용하는 방식. sparse한 데이터에 적합합니다.
            2. Manhattan Distance / Euclidean Distance : Missing value가 적을 때 효과를 발휘한다. dense한 데이터에 많이 사용합니다.
            3. Pearson Correlation Coefficient : grade-inflation 이 있는 곳에 적합합니다.
        * 저희의 점수 입력방식은 학생들이 모든 데이터를 입력할 것이란 보장이 없기에 sparse한 데이터 구조를 띄게 될 것입니다.
            * 그래서 시작을 Cosine-similarity로 하게 되었습니다.
            <img src = '/img/cos.png'/>
                * 내적공간의 두 벡터간 각도의 코사인 값을 이용하여 유사한 정도를 측정
                * 두 벡터의 방향이 같으면 1, 완전히 다른 반대가 될 경우 -1, 독립적인 경우 0
                * 양수 공간이라는 조건만 만족하면 얼마나 많은 차원 공간에서든지 사용가능
                <img src = '/img/cos2.png' width = 500/>
                <img src = '/img/cos3.png' width = 600/>
                * 계산 예제입니다.
                <img src = '/img/cos4.png' width = 600/>
                * 예측점수 계산 예제입니다.
                * 각 유저끼리의 유사도를 구하여 그 유사도와 전체 유사도의 합의 비율에 점수를 곱하여 예측점수를 내게 됩니다.
    * 구현방식
        1. 먼저 개인의 강의 성향을 파악하기 위해 수강했던 과목에 점수를 입력하게 됩니다.(1점 ~ 5점)
        2. 입력받은 점수를 기반으로 각 사용자들과 Similarity를 구하게 됩니다. 이 방식으로 Cosine-similarity를 사용합니다.
        3. 유사도를 구하여 가장 유사도가 높은 K명의 집단을 구합니다.
            * 여기서 저희는 계산횟수와 신뢰성을 높이기 위해 과 내에서 검색을 하게 됩니다.
            * 현재 구현 상태에서는 10명의 유사집단으로 계산하게 됩니다.
        4. K명의 유사집단 내에서 제가 듣지 않은 과목을 찾고 그 과목에 해당하는 예상 평점을 유사도를 이용하여 계산합니다.
        5. 이후 이 예상 평점이 높은 과목을 추천하게 됩니다.
            * 만약 그 과목을 수강하고 이후에 그 과목에 대한 평점을 입력 했을 때 MAE를 계산하게 됩니다.
            * 주기적으로 유저의 MAE를 확인하여 제대로 추천이 되고 있는지 판단하여 알고리즘을 개선합니다.
    * 성과 측정 방식 : **MAE(Mean Absolute Error)**
        <img src = '/img/mae.png'/>
        * 수치적 데이터 평가방법
        * 예측점수와 실제 평가점수의 차를 받아 과목, 유저수로 나눠 평균 오차율을 계산합니다.
- 가용 가능한 data sources
    - sugang.inha.ac.kr에서 수강가능한 시간표
        - 크롤링 후 가공하여 사용
    - 에전 총 학생회에서 조사한 주관식 교양 백서
        - 사용불가
    - 인하대학교 정보통신처에서 학생들의 수강신청 기록들
        - 위 사항은 정보통신처에서 연락을 주지 않아 불가능할 것으로 예측됩니다.
    - '인하대학교 시간표'에서 데이터 요청
        - 작년 가을 시간표 데이터로 사용
    - 크롤링한 데이터를 바로 사용할 수 있는 상태가 아니기 때문에 가공하여 사용
    - 학생들이 입력한 데이터
        - 이 데이터를 기반으로 추천을 하게 됩니다.

- DB구성 예정(다음페이지 상세)
<img src = '/img/db.png' height = 1030/>

### 개발 결과
- 최종 결과물에 대한 스크린샷
    #업데이트 필요#

    <img src = '/img/res1.png'/>
    * 로그인 화면입니다.

    <img src = '/img/res2.png'/>
    * 회원가입 화면입니다.

    <img src = '/img/res3.png'/>
    * 비밀번호 찾기 화면입니다.

    <img src = '/img/res4.png'/>
    * 비밀번호 찾기 두번째 화면입니다.

    <img src = '/img/res5.png'/>
    * 찾기를 요청하면 메일로 오게 됩니다.

    <img src = '/img/res9.png'/>
    * 비밀번호 수정이 가능해 진 화면입니다.

    <img src = '/img/res6.png'/>
    * 평가 화면입니다.

    <img src = '/img/res7.png'/>
    * 평가한 강의를 볼 수 있는 화면입니다.

    <img src = '/img/res8.png'/>
    * 강의를 추천해주는 화면입니다.

    <img src = '/img/res10.jpeg' height=500/>
    * 모바일 환경 화면입니다. 로그인 화면입니다.

    <img src = '/img/res11.jpeg' height=500/>
    * 모바일 환경 화면입니다. 평가 화면입니다.

    <img src = '/img/res13.jpeg' height=500/>
    * 모바일 환경 화면입니다. 평가한 것을 보여주는 화면입니다.

    <img src = '/img/res12.jpeg' height=500/>
    * 모바일 환경 화면입니다. 추천 받기 화면입니다.

- demo 동영상 youtube 링크
    * 링크 : https://youtu.be/NfAYpNKgrYk
    * 느린속도 동영상 링크 : https://www.youtube.com/watch?v=xTLkatgDOXE
- 테스트 결과 (정량적 수치 및 객관적 데이터 제시)
    * 추천 서버와 Application 서버의 통신 정도
        * SQS 그래프 보여주기
        * #업데이트 필요#
    * MAE 수치
        * ~일 ~개의 과목, ~명의 데이터 : MAE수치 ()
        * #업데이트 필요#


### 결론
* 향후 활용 방안
    * 짧게는 다음학기 길게는 계속되는 수강신청 시기에 강의 추천 및 시간표 작성이 가능해집니다.
    * 데이터가 많이 쌓이면 쌓일수록 유저는 더 나은 추천을 받게 됩니다.
* 추가 진행 및 개선 방안
    * 강의 평가에 대한 코멘트를 넣어 opinion mining을 통한 좀 더 구체적인 추천을 해보려고 합니다.
    * 학생들의 악의적으로 입력하는 데이터의 필터링 문제가 있습니다.
    * 학생들의 지속적인 유입 방안 필요합니다.
* 프로젝트 진행하면서 느낀 점
    * 데이터를 수집하는 과정이 너무 짧아 개선되는 모습을 많이 담지 못해 아쉬운것 같습니다.
    * 프로젝트를 완성하여 약 100명 정도의 사용자를 받고 서비스를 제공하여 좋은 경험이었습니다.

##### 참고문헌

1. guide to datamining, "recommendation system tutorial", http://guidetodatamining.com/
2. 인사이드 자바스크립트, "javascript tutorial ",http://www.hanbit.co.kr/store/books/look.php?p_code=B6479856408
3. jump to python, "python tutorial", https://wikidocs.net/2
4. Redux offical document, "redux document", http://redux.js.org/
5. BeautifulSoup4 official document, "BeautifulSoup document ", https://www.crummy.com/software/BeautifulSoup/bs4/doc/
6. facebook official React document, "react document", https://facebook.github.io/react/
7. Webpack2 offical document, "webpack document", https://webpack.js.org/
8. Express official document, "Express document", https://expressjs.com/en/api.html
9. Mostly adequate guide to FP(in javascript), "FP js",https://www.gitbook.com/book/drboolean/mostly-adequate-guide/details
10. mysql-python connector overview, "python mysql connector", https://dev.mysql.com/doc/connector-python/en/connector-python-connectargs.html
11. Amazon Web Service official Document, "AWS", https://aws.amazon.com/ko/documentation/
12. Stanford Jeffrey D. Ullman mining massive datasets, "Recommendation System", http://infolab.stanford.edu/~ullman/mmds/ch9.pdf
13. 카이스트 제 8회 ROSAEC 워크샵자료 Recommendation System "협업 필터링을 중심으로", http://rosaec.snu.ac.kr/meet/file/20120728b.pdf
14. GroupLens Research Group / Army HPC Research Center. *"Application of Dimensionality Reduction in Recommender System -- A Case Study"*, WebKDD-2000 Workshop, 2000
15. Mean absolute error, "Mean Absolute Error",https://en.wikipedia.org/wiki/Mean_absolute_error#cite_note-:0-1
