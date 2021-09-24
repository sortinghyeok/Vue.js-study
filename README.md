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

