<img width="1277" alt="레이아웃" src="https://user-images.githubusercontent.com/48181483/95404244-77afac00-094f-11eb-935e-3229ac85f907.png">

위 이미지를 분석하며 퍼블리싱 해보겠습니다. 



규칙 1. css 클래스 네이밍은 케밥케이스 사용(css 자체가 소문자 + '-' 하이픈의 조합)

-> 문서 편집기에서도 하이픈 작동, 선언의 일관성,

​         2 css id 네이밍은 카멜케이스 사용()

자바스크립트 코드에 id 사용할일이 많으므로 (window.localStorage, document.querySelect)

3. chrome extension에 Web develop의 Display ruler 기능을 사용하여 너비,높이를 측정하였습니다

   ->고정형 px단위 사용


4. 아이콘은 fontaswome사용



HTML 구조부터 작성해보았습니다.

```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title>publishing</title>
    <link rel="stylesheet" href="./css/style.css">
</head>
<body>    
    <div class="container"><!--ⓐ-->
        <div class="main"> <!--ⓑ-->
            <header></header> <!--ⓒ-->
            <div class="profile"></div> <!--ⓓ-->
            <div class="name-card"></div> <!--ⓔ-->
            <div class="more-btn"></div> <!-- ⓕ-->
            <div class="direct-message"></div> <!--ⓖ-->
            <div class="another-page"></div> <!--ⓗ-->
        </div>
    </div>
 </body>

</html>
```

가장최상단의 하늘색(?)을 가장밖에 깔리는 배경으로 보았으나 body태그에 직접적으로 배경을 입히지 않기 위해 '디자인용' div를 만들어 container라고 네이밍하였습니다. ⓐ

안에 흰색을 메인컨텐츠로 ⓑ 높이에 따라 큰틀을 잡으며 메인콘텐츠에 포함되는 마크업을 진행하였습니다.

ⓒ에는 네비게이션과 글쓰기(?)로 분석되는 컨텐츠가 들어갈 예정이며

ⓓ에는 프로필(사진), ⓔ에는 명함 + 자기소개 ⓕ더보기버튼 ⓖ페이스북/메일등 DM ⓗ다른 웹사이트로 

이동 기능을 넣을 예정으로 마크업을 1차 완료하였습니다.

```css
@charset 'utf-8';

*{
    margin:0px;
    padding:0px;
}

ol,ul{
    list-style: none;
}

a{
    text-decoration: none;
}

body .container{
    background-color: skyblue;
    padding:25px;
}

.container .main{
    background-color: white;
    width:380px;
    height:610px;
    margin: 0px auto;
}

.main header{
    background-color: red;
    height:50px;
    padding:10px;
}

.main .profile{
    background-color: orange;
    height:220px;
}

.main .name-card{
    background-color: yellow;
    height:70px;
}

.main .more-btn{
    background-color: green;
    height:60px;
}

.main .direct-message{
    background-color: blue;
    height:90px;
}

.main .another-page{
    background-color: purple;
    height:60px;
}

```



.container 위의 코드들은 reset.css의 일부만 사용하였습니다.



모든 css선택자는 가장가까운 부모+자신의 조합으로 작성해서 우선순위를 높이되,  길어지지 않게하였고 (좋은지 의문이 듭니다 나중에 변경될 수 있음)



<img width="1277" alt="initial layout" src="https://user-images.githubusercontent.com/48181483/95405381-96637200-0952-11eb-904d-db799bdc5229.png">



body태그에 직접적으로 background속성을 사용하지 않으려는 시도 때문에 container의 높이가 자식의 main태그들의 높이의 합을 자동으로 계산하여 영역을 유지하기 때문에 배경전체를 뒤덮지는 못했습니다( 추후 해결할문제)






