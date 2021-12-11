# 프로젝트 설계 과정
## 블로그용 Repo 만들기
1. dla020501.github.io 이름의 repository를 public으로 생성.
2. git clone을 사용하여 /home/git/bloggame/blog 폴더와 연동시킴.

## Jekyll 환경 구성
1. Jekyll 공식 사이트 https://jekyllrb-ko.github.io/ 을 통해 Jekyll과 bundler젬을 설치.
2. /home/git/bloggame/blog 폴더로 이동.
3. 현재 폴더에 새 Jekyll 사이트를 생성.
`jekyll new . --force` 
4. 사이트를 설계하고 로컬 서버에 적용하기 위해서는 다음의 명령어를 실행하면 됨.
`bundle exec jekyll serve`
5. 사이트를 설계하고 git으로 push하면 dla020501.github.io 링크를 통해 설계한 사이트 확인 가능.

## 테마 적용하기
http://jekyllthemes.org/ 사이트의 What A THeme 테마 적용.
1. https://github.com/thedevslot/WhatATheme 에서 git clone을 사용하여 /home/git/bloggame/WhatATheme 경로로 받아옴.
2. 받아온 테마를 blog 폴더에 덮어쓰기를 하되, 의존성을 감안하여 _posts 폴더를 제외함.
3. 테마 파일들을 git으로 push함으로써 테마 적용

## 테마 수정하기
