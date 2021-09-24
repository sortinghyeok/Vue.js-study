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

###2. Project Structure
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
Components
컴포넌트는 기본 html elements를 확장하고, 재사용화하게 하기위해 캡슐화 하는데에 목적이 있다.
그러나 지금은 초기 단계이므로, SFC인 .vue file에 집중하기로 하고 언급만 하고 넘어가기로 한다.

---------------------------------------------------
Script

![image](https://user-images.githubusercontent.com/80696846/134664408-dccb709b-d5fe-41e6-8571-362b5156f3c4.png)

위 이미지에서는 data()라는 함수를 선언해주었다. 스크립트 내에는 이와 같이 template에 보내줄 로직, 데이터 등을 작성할 수 있다.

