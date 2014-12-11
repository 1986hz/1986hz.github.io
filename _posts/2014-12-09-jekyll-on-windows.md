---
layout: post
title:  "윈도우에서 github와 jekyll을 이용하여 블로그 만들기"
date:   2014-12-09 22:18:25
categorie: blog
---

마크다운을 이용한 문서를 가독성이 높다는 것을 알게 되었다. 그래서 나는 github와 jekyll을 이용하여 블로그를 만들기로 결심했다. 구글 검색을 통해 jekyll pygment windows github로 검색하면 많은 자료를 얻을 수 있다. 하지만 윈도우환경과 jekyll버전에 따라 다양한 error가 발생하는 것 같았다. 나는 다음에 다시 jekyll을 설치해야 하거나 windows에서 jekyll을 사용하고 싶은 이들에게 도움이 되고자 이 문서를 작성한다.

> 이 문서대로 jekyll을 설치하고 `jekyll serve`로 서버를 실행시키면 'which'를 찾을 수 없다는 warining이 발생한다. 하지만 실제작동에는 문제가 없는 것으로 같으니 정신건강을 위하여 그냥 사용하기로 하였다.


## 참고사이트
- [Junhilo : Run jekyll on Windows](http://jekyll-windows.juthilo.com/)
- [YiZeng : Setup jekyll on Windows](http://yizeng.me/2013/05/10/setup-jekyll-on-windows/)


## Ruby 설치하기
1. [http://rubyinstaller.org/downloads/](http://rubyinstaller.org/downloads/)로 간다.
2. RubyInstallers탭에서 `Ruby 2.0.x-pxxx`설치파일을 다운 받는다. 만일 Windows 64bit인경우 `Ruby 2.0.x-pxxx (x64)`를 다운 받는다. 
    > Windosws 64bit면 꼭 64bit설치파일을 다운 받자!
3. DEVELOPMENT KIT탭에서 Windows환경과 Ruby버전에 맞는 파일을 다운 받는다.
    > 64bit는 DevKit-mingw64-64-xxxx.exe를 다운 받는다!
4. 다운 받은 Ruby를 설치한다.
    - 설치설치경로는 `c:\Ruby200`과 같이 공백이 없어야 한다.
    - `Add ruby executables to your PATH`를 체크하여 PATH한다.


## DevKit 설치하기
1. Ruby의 DEVELOPMENT KIT를 실행시켜 `C:\DevKit`과 같이 압축을 푼다.
2. 터미널에서 `cd c:\devkit`로 해당폴더로 이동한다.
3. 터미널에서 `ruby dk.rb init`를 입력하여 초기화를 한다.
4. 터미널에서 `ruby dk.rb install`를 입력하여 설치를 한다.


## jekyll 설치하기
1. 터미널에서 `gem install github-pages`를 입력한다.
> `gem install jekyll`로도 설치할 수 있지만 github-pages는 jekyll을 포함하여 github의 pages에서 지원되는 많은 gem들도 쉽게 설치할 수 있도록 도와준다.


## python 설치하기
github의 pages에서는 syntax highlighter로 pygments를 사용하기 때문에 꼭 pygments를 설치해야 한다.
1. [https://www.python.org/downloads/](https://www.python.org/downloads/)에서 `python 2.7.x`설치파일을 다운 받는다.
2. 다운 받은 python설치파일을 설치한다.
    - 설치경로는 `c:\python27`과 같이 공백이 없어야 한다.
    - 설치목록에서 Add python.exe to Path를 선택한다.


## Pygments 설치하기
1. [https://pip.pypa.io/en/latest/installing.html](https://pip.pypa.io/en/latest/installing.html)에서 `get-pip.py`를 다운받는다.
2. 터미널에서 get-pip.py를 다운 받은 곳으로 이동한다.
3. 터미널에서 `python get-pip.py`를 입력하여 pip를 설치한다.
4. 터미널에서 `python -m pip install Pygments`를 입력하여 Pygments를 설치한다.
    > 만일 Pygments 설치를 실패하였다면 python scripts를 Path하고 다시 설치를 시도해보자!


## python scripts를 Path하기
1. 바탕화면의 내컴퓨터를 오른쪽클릭하여 속성을 선택한다.
2. 고급시스템설정을 선택한다.
3. 환경변수를 선택한다.
4. 사용자변수 탭에서 편집을 선택한다.
5. 변수 값 필드의 마지막에 `;C:\Python27\Scripts`를 붙여 넣는다.
    > 자신이 설치한 python의 설치경로에 따라서 값이 다를 수 있다.
6. 확인눌러 저장한다.


## Github 저장소 만들기
Github의 Pages는 **개인/조직 Pages**와 **프로젝트 Pages**로 나뉜다. 사용방법이 다르니 여기서는 **개인/조직 Pages**만 설명하겠다.

1. [Github](https://github.com/)에 가입을 한다.
2. 가입한 메일사이트에 접속하여 가입인증을 한다.
    > 가입인증을 하지 않으면 Pages가 올바로 작동하지 않는다!
3. `아이디.github.io`로 저장소를 만든다.
4. [Github for windows](https://windows.github.com/)에서 설치파일을 다운받고 설치한다.
5. 바탕화면에서 설치된 GitHub프로그램을 실행하고 각종 정보를 입력한다.
    > 특히 configure git의 아이디와 이메일정보가 중요하다!


## 로컬에 jekyll로 블로그 만들기

1. 터미널에서 `c:\`를 입력하여 c:\로 이동한다.
    > 다른경로를 사용하여도 상관없다!
2. 터미널에서 `jekyll new 아이디.github.io`를 입력하여 `아이디.github.io`폴더를 만들고 jekyll에서 사용하는 각종파일을 설치한다.
3. 터미널에서 `cd c:\아이디.github.io`를 입력하여 `아이디.github.io`폴더로 이동한다.
4. 터미널에서 `jekyll serve`를 입력한다.
    > 이때 `wdm gem`이 설치되지 않았다고 출력이 나오면 터미널에서 `gem install wdm`을 입력하여 `wdm`을 설치한다. 'which'는 서론에서 적었듯이 그냥 넘어가도록 한다.
5. 브라우저에 `localhost:4000`를 입력하여 서버에 접속하면 블로그를 볼 수 있다.


## Github에 Push하기
이제 Github에 블로그를 Push해보자. Push하면 `https://아이디.github.io`로 어디서든 자신의 블로그에 접근할 수 있다.

1. 터미널에서 `cd c:\아이디.github.io`로 이동한다.
2. 터미널에서 `git init`를 입력하여 git를 초기화한다.
3. 터미널에서 `git add .`를 입력하여 git에 모든 파일을 추가한다.
4. 터미널에서 `git remote add https://github.com/아이디/아아디.github.io.git`를 입력하여 저장소를 추가한다.
5. 터미널에서 `git push`를 입력하여 github에 게시한다.


## https://아이디.github.io 접속하기
- Push한다고 Pages가 바로 작동하지 않고 약 10분정도의 시간이 걸리다.
- 저장소의 settings에 들어가면 pages가 올바른지 확인할 수 있다.
- pages가 올바르게 작동하지 않으면 가입한 메일로 무엇이 잘못되었는지 간략하게 메일이 온다.


## 이제 블로깅하자!
이제 jekyll을 이용하여 블로그를 운영할 준비가 되었다. 하지만 내가 원하는대로 블로그를 수정하려면 아직도 해야 할 일이 많은 것 같다. 그래도 마크다운을 이용하여 문서를 작성하고 블로그로 관리할 수 있다는 사실에 너무 기쁘다 :)