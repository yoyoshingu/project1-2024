# project1-2024
2024-2학기 캡스톤프로젝트 수업
OpenAPI를 사용한 인공지능 시스템 실습

<img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=HTML5&logoColor=white">
<img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=CSS3&logoColor=white">
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=JavaScript&logoColor=white">
<img src="https://img.shields.io/badge/Visual Studio Code-007ACC?style=flat-square&logo=Visual Studio Code&logoColor=white"/>
<img src=https://img.shields.io/badge/jquery-%230769AD.svg?style=for-the-badge&logo=jquery&logoColor=white/>


# openweathermap

지정된 장소의 현재 날씨를 표시
https://api.openweathermap.org/data/2.5/weather?q=london&units=metric&appid=7d96bc5108f52b80e2d9075a369b9f35
- [실습해보기](https://api.openweathermap.org/data/2.5/weather?q=london&units=metric&appid=7d96bc5108f52b80e2d9075a369b9f35)

```javascript
$.ajax({
			type: "GET",
			url: 'https://api.openweathermap.org/data/2.5/weather?q=london&units=metric&appid=7d96bc5108f52b80e2d9075a369b9f35',
		}).done(function(response) {

            console.log(response)
 
		}).fail(function(error) {
			alert("!/js/user.js에서 에러발생: " + error.statusText);
		});



```
# openAI

OpenAI에서 제공하는 텍스트생성 및 이미지 생성 실습
텍스트생성

```javascript
squestion = txtMsg.value
    data ={
        model: smodelmini,
        messages: [
            {
                role: "user",
                content: squestion
            }
        ]
    }

    $.ajax({
        type:"POST",
        url: "https://api.openai.com/v1/chat/completions",
        headers:{
            "Authorization": "Bearer " + OPENAPI_KEY
        },
        data: JSON.stringify(data),
        contentType: "application/json; charset=utf-8"
    }).done( function(response){
        console.log(response)

    }).fail(function(error){
        console.log(error)

    })
```

이미지생성

```javascript
squestion = txtMsg.value
    data ={
        prompt: squestion,
        n: 2,
        size:"512x512"
    }

    $.ajax({
        type:"POST",
        url: "https://api.openai.com/v1/images/generations",
        headers:{
            "Authorization": "Bearer " + OPENAPI_KEY
        },
        data: JSON.stringify(data),
        contentType: "application/json; charset=utf-8"
    }).done( function(response){
        console.log(response)

        gimage.src = response.data[0].url
        gimage2.src = response.data[1].url
    }).fail(function(error){
        console.log(error)
    })
```

# google cloud vision

구글에서 제공하는 이미지 분석 프로그램
```javascript
data ={
        requests: [{
            image:{
                content: imagestring
            },
            features:[{
                type:"FACE_DETECTION",
                maxResults: 100
            }]
        }]
    }

    $.ajax({
        type:"POST",
        url:'https://vision.googleapis.com/v1/images:annotate?key=' + VISION_API_KEY,
        headers:{
            "Accept": "application/json",
            "Content-Type": "application/json"
        },
        data: JSON.stringify(data),
        contentType: "application/json; charset=utf-8"
    }).done( function(response){
        console.log(response)

    }).fail(function(error){
        console.log(error)

    })
```

개발순서
1. 소스수정
2. 소스 저장
3. 스테이지
4. 커밋애 푸쉬
5. 커밋메시지


**git 설정** <br>
git config --global user.name "Lee"
git config --global user.email "leo@shingu.ac.kr"


두번째 수정

2024-9-19 깃허브연동실습
로컬에서 편집함
