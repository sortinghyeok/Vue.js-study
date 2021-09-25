본 스터디는 Code volution의 Vue JS 3 Tutorial을 참고하였으며, 프론트엔드 공부에 목적을 둔다.

## 1. 개발 환경 설치

vue.js의 프로젝트 환경을 만드는 방법은 크게 4가지가 있으나, 이번 공부에서는 vue/cli를 이용하기로 한다.

가장 우선적으로 해야하는 것은 node.js를 설치한 후, 관리자 권한의 cmd창 또는 terminal을 이용해 vue.js를 설치하는 것이다.
vue.js를 설치하는 방법은 다음과 같다.

---------------------------------------------

1. yarn global add @vue/cli
or
2. npm install -g @vue/cli
이때, 후자의 경우 vue가 설치되는 경로가 나타나는데 이 경로를 환경변수로 추가해줘야 vue명령어가 터미널에서 작동하므로 주의해야한다.

만일 이전에 구 버전의 node.js가 존재하거나, 이미 설치된 vue.js가 있었다면 vue3 버전의 vue.js가 설치되지 않을 수 있다.
이 경우, 다음의 순서를 따르면 vue3버전을 다운로드할 수 있다.
1. npm uninstall -g vue-cli //@가 없는 것이 맞다.
2. npm install -g @vue-cli

설치가 완료되면, 이제 vue 3의 command인 create를 사용할 수 있다.
순서는 다음과 같다.

1. vue create hello-world
2. version 선택
3. 설치 완료됨

위 순서에 따라 이제 hello-world라는 프로젝트가 만들어졌다. 이제 터미널 기본 명령어인 cd를 이용해 hello-world로 이동해준다.
명령은 다음과 같다.

1. cd hello-world

react study에서도 그랬듯이, 우리는 이제 패키지 매니저 툴인 yarn과 npm 등을 이용해 개발 서버를 연동해주어야 한다.
방법은 다음과 같다.

1. yarn serve
or
2. npm run 

이제 우리는 vue.js를 이용한 기본적인 개발 서버를 연결했다.
default는 http://localhost:8080/이 된다.

-------------------------------------------------

## 2. Project Structure
타 Stacks에서와 같이, 프로젝트를 create하고 나면 package.json파일에서 dependencies를 확인할 수 있다.

yarn.lock 파일은 dependency를 버전에 맞춰 설치하는데에 목적이 있으므로, 개발 과정에 있어 필요하지 않으면 그대로 두게 될 것이다.

babel.config.js파일은 우리가 쓰는 modern js 코드를 old js와 맞춰주는 역할을 한다.
즉, babel로 인하여 구 버전에서 작성한 코드와 호환이 가능하게 되는 것이다.

node_modules는 package.json에 적혀있는 dependencies들에 대해 파일들이 설치되는 디렉토리이다.

public은 application실행시에 보여줄 디자인 부를 가지고 있다. 이 곳에는 html 파일이 존재하며, 통신상에서의 object가 된다.
html의 태그는 디자인 코드의 적용에 있어 그 적용범위가 되는 부분이므로, 차후 공부하게 된다.

src 폴더는 대부분의 기능을 저장하는 디렉토리이다.
프로젝트 내부에는 main.js와 같은 핵심적인 기능부가 존재하며, 이 내부에 존재하는 컴포넌트 app은 root dom node로써 기능하여 html부에
영향을 주게 된다.
App.vue는 프론트엔드의 ui의 부분이 되는 html, css, 그리고 js를 specify한다.
또 하나의 기본 .vue 파일인 hHelloWorld.vue파일은 타 페이지로 이동하는 링크들을 가지고 있다.
asset 폴더에는 이미지와 같은 것들이 들어가며, ui에 있어서 필요한 소스를 저장하는 역할을 한다.

---------------------------------------------------------------
.Vue file 

.vue 파일은 vue.js에서 제공되는 custom file type으로, html-like syntax를 가진 ui portion format 제작에 이용된다.
.vue 파일은 세 가지 타입의 top-level language blocks가 존재하는데, 그 세가지는 아래와 같다.

1. <template></template>
2. <script></script>
3. <style></style>

template block은 html과 같은 역할을 하며, 스크립트의 structure을 정의한다.
script block은 js와 같은 로직, 데이터를 maintain하는데에 목적이 있다.
style block은 ui 디자인을 markup하는 부분으로, 전체적인 디자인을 담당한다.

-----------------------------------------------------
## Components
컴포넌트는 기본 html elements를 확장하고, 재사용화하게 하기위해 캡슐화 하는데에 목적이 있다.
그러나 지금은 초기 단계이므로, SFC인 .vue file에 집중하기로 하고 언급만 하고 넘어가기로 한다.

---------------------------------------------------
## Script

![image](https://user-images.githubusercontent.com/80696846/134664408-dccb709b-d5fe-41e6-8571-362b5156f3c4.png)

위 이미지에서는 data()라는 함수를 선언해주었다. 스크립트 내에는 이와 같이 template에 보내줄 로직, 데이터 등을 작성할 수 있다.

## Binding Text

![image](https://user-images.githubusercontent.com/80696846/134759370-d01f5b9c-4c24-4fb5-ac30-79bac7e1491b.png)

스크립트 내에 위와 같이 객체가 선언되었다고 하자. 그러면 이 객체의 이름은 name이고, 그 content는 Vishwas가 될 것이다.
이를 template 내부 이중 중괄호 {{}} 안에 넣어주게 되면, {{name}}에서 Vishwas가 hello 다음에 출력됨을 확인할 수 있다.

![image](https://user-images.githubusercontent.com/80696846/134759409-d8597e71-10be-4058-bdff-a5b0f0385fac.png)

이의 강력한 점은, 이는 정적인 것이 아니라 name 속성이 변경될 때마다 update 된다는 점이다.
이제 또다른 binding 방법인 v-text에 대해서 살펴보도록 하자.

![image](https://user-images.githubusercontent.com/80696846/134759596-553a6d9e-285d-4f25-8200-a0772eb8cf8c.png)

여기서 v-text는 브라우저에 sortinghyeok으로 출력된다. 그러나 v-text의 단점은 다음과 같다.

![image](https://user-images.githubusercontent.com/80696846/134759625-7997c592-c9a9-403e-b86a-c60fcfc9ad55.png)

바로 이전의 코드에서 <div>태그 사이에 텍스트를 입력했을 뿐이지만, v-text는 블록내부의 전부를 태그 내부의 콘텐츠로 덮으려고 시도하기에 이에 충돌이 일어나게 된다. 따라서 v-text는 동적인 바인딩에 제약이 있다는 단점이 있다.
또한, 이중 중괄호 문법은 v-text에 비하여 처리속도가 약간 더 빠르다는 이점이 존재한다.
  
## Binding HTML
위에서 이미 우리는 v-text를 공부해보았다. 이와 비슷한 부류로, v-html을 공부해본다.
v-html은 script 태그 내부에 존재하는 객체에 태그를 씌워 효과를 줄 수 있다.
bold tag인 <b> 태그를 channel에 입혀본다.

![image](https://user-images.githubusercontent.com/80696846/134759854-2f222a97-207f-47fa-ad87-2ba6d52202d7.png)
  
![image](https://user-images.githubusercontent.com/80696846/134759855-8a6d8443-113c-485c-b86e-61f188527324.png)

![image](https://user-images.githubusercontent.com/80696846/134759862-39f32920-7b6c-41e4-8538-aadf88842f9d.png)
  
위와 같이 bold 효과가 sortinghyeok text에 나타났다. channel 객체에 즉각적으로 영향을 준 것이다.
  
## Binding Attributes

v-bind를 알아보자. 
  
![image](https://user-images.githubusercontent.com/80696846/134760076-c31d5a91-740a-41fa-a125-ffdc12eae8af.png)

![image](https://user-images.githubusercontent.com/80696846/134760086-e850ea45-8544-4e4a-bd52-3903fdfc06c3.png)

위와 같은 상황에서, Heading의 id는 heading이 된 것을 확인할 수 있다.
이 외에도, v-bind는 타 속성, 예를 들면 boolean 타입 속성을 binding 할 수 있다. 아래 예시를 보자.
  
![image](https://user-images.githubusercontent.com/80696846/134760151-4814e7fe-2c0a-4153-bdf3-3f0bfaa30639.png)

data() 내의 return 객체 isDisabled가 true 또는 false인 것에 대하여, v-bind:disabled = "isDisabled"는 해당 버튼을 활성화할지, 또는 비활성화할 지를 결정할 것이다.

1. false
![image](https://user-images.githubusercontent.com/80696846/134760189-ee4fcd29-0542-4dab-8f1c-5cb93f025e18.png)

2. true
![image](https://user-images.githubusercontent.com/80696846/134760196-b15ed290-c771-4cbb-8ed3-a9b9640cd2d6.png)

-----------------------------------
  
## Binding Classes
 
![image](https://user-images.githubusercontent.com/80696846/134760459-44b16684-dbfa-4bc5-9d44-e94cc201c589.png)

위와 같이 style tag 내에 class를 선언하고, 아래와 같이 사용한 경우
  
![image](https://user-images.githubusercontent.com/80696846/134760500-c14943f5-415b-46fd-adf8-78d1b99fa6ec.png)

정적인 클래스를 이용할 수 있으며 이는 바뀌지 못한다. 때문에 우리는 동적인 클래스 바인딩을 위하여 data() 내부 return 객체를 다시 이용해줄 것이다.

![image](https://user-images.githubusercontent.com/80696846/134760603-bb0e2709-8c3f-428b-ad9a-4815b6773094.png)

위와 같이 status 객체를 선언하고, 
  
![image](https://user-images.githubusercontent.com/80696846/134760626-785d206d-9637-4d29-a2e5-27579b0f7e8f.png)
  
위처럼 v-bind를 이용해 v-bind:class="status"로 지정해주면, status 내부의 값이 바뀔 때마다 내부 binding된 클래스가 바뀌게 된다.
그리고 우리는 여기서 그치지 않고 이중 바인딩을 해줄 수 있는데, 기존에 선언한 underline class를 h2 태그 바로 옆에 붙여주면 
![image](https://user-images.githubusercontent.com/80696846/134760697-867eb2b9-38d6-4378-ba09-93db14ad8a69.png)

위와 같은 결과를 얻을 수 있어 여러 클래스를 동시에 접목시킬 수 있다.
또한, 이러한 클래스가 적용되는 것을 조건부로 지정할 수 있는데, 이를 conditional binding이라고 한다.
  
![image](https://user-images.githubusercontent.com/80696846/134760744-268378d4-2571-41d1-9de2-180dc8b8c71b.png)
  
위와 같이 새 클래스를 선언해주었다. 이제 template tag 내부에 새로운 h2태그 내부 조건부 바인딩을 해본다.
  
![image](https://user-images.githubusercontent.com/80696846/134760785-39a6c030-18ed-4df9-a283-f385c3ca4856.png)

위와 같이, && 연산자를 이용해 isPromoted가 false냐 true냐에 따라서 클래스를 적용시킬 수 있다. 이제 저 태그 사이에 들어가는 텍스트는 isPromoted가 true면 이탤릭체로 기울어질 것이고, false라면 그렇지 않을 것이다.
아래는 삼항 연산자를 이용한 클래스 적용이다.
  
![image](https://user-images.githubusercontent.com/80696846/134760994-7d5534ec-1826-424f-9c39-598b72a2a842.png)

 1. true
 
 ![image](https://user-images.githubusercontent.com/80696846/134761016-60a880f5-9e80-488f-b3fe-1c86a3515fbe.png)
  
 2. false
 
 ![image](https://user-images.githubusercontent.com/80696846/134761005-f41ce569-a3fb-4353-9ec8-12466a3bb006.png)

또한 v-bind는 배열 내부에 클래스를 묶어 사용할 수 있다.

![image](https://user-images.githubusercontent.com/80696846/134761077-2cabf50d-bca2-4212-a24e-0f342d03b379.png)

 ![image](https://user-images.githubusercontent.com/80696846/134761086-faebcf36-99b9-4181-9781-9f859e38bdb8.png)

위와 같이 사용할 경우, v-bind 내부에 두 개의 클래스가 모두 적용되었음을 확인할 수 있다.
또한, 객체 기반의 바인딩도 가능한데 그것은 아래와 같다.

![image](https://user-images.githubusercontent.com/80696846/134761524-75f2e322-bc39-4eea-b24d-19dbb7ce7473.png)

객체 내부에 각 변수에 해당하는 조건을 서술해줌으로써, 클래스 : 조건의 형식으로 작성해 조건이 성립할 시 해당 클래스가 발동되는 형식이다.
  
