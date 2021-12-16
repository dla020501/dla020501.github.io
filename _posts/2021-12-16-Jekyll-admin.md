---
layout: post
tag: Jekyll-admin, Information
title: Jekyll-admin
---

# Jekyll-admin
## Jekyll-admin이 무엇인가?
콘텐츠를 작성하고, Jekyll 사이트를 관리할 수 있는 기존 CMS 스타일 그래픽 인터페이스를 사용자에게 제공하는 Jekyll 플러그인이다.

## 설치 방법
1. 터미널 내에서 Jekyll 환경 구성을 완료한 폴더로 이동한다. 여기서는 /home/git/bloggame/blog 폴더를 기준으로 설명함.
2. Gemfile 파일을 텍스트 편집기로 열어서 다음과 같은 명령어를 추가한다.
```
group :jekyll_plugins do
  gem 'jekyll-admin', "0.9.0"
end
```
3. plugin 설치를 한다.

`bundle install`

4. 설치가 완료되면 jekyll을 실행 시킨다.

`jekyll serve`

5. 브라우저에서 localhost:4000/admin 으로 접속시 다음과 같이 관리 화면이 표시가 된다.

![Jekyll-admin 실행화면](https://user-images.githubusercontent.com/84278264/146332144-b6b65595-6e3d-4488-a8c6-3a53cebafa62.png)
