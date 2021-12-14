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
http://jekyllthemes.org/ 사이트의 What A Theme 테마 적용.
1. https://github.com/thedevslot/WhatATheme 에서 git clone을 사용하여 /home/git/bloggame/WhatATheme 경로로 받아옴.
2. 받아온 테마를 blog 폴더에 덮어쓰기를 하되, 의존성을 감안하여 _posts 폴더를 제외함.
3. 테마 파일들을 git으로 push함으로써 테마 적용

## 테마 수정하기
### 불필요한 메뉴 버튼 삭제
What A THeme 테마에는 HOME, ABOUT, CONTACT, BLOG, MORE 안의 Projects, Test Page의 메뉴 버튼들로 구성되어 있음.
이 중 메인 화면을 표시하는 HOME, 블로그 주인에 대한 설명이 있는 ABOUT, POST들을 모아놓은 BLOG 총 3개의 메뉴 버튼을 사용.
1. _includes 폴더의 navbar.html 파일을 텍스트 편집기로 다음과 같이 수정.
2. `<a class="navbar-item" href="{{site.url}}{{site.baseurl}}/#contact">CONTACT</a>`를 지워서 CONTACT 버튼을 없앰.
3. `{% include dropdown.html %}`를 지워서 MORE의 Projects, Test Page를 담당하는 dropdown.html을 포함시키지 않도록 함. 
4. _includes 폴더의 contact.html, dropdown.html, project-card.html 파일을 삭제함.
5. _layouts 폴더의 default.html에서 `{% include contact.html %}` 를 지워서 CONTACT 내용이 뜨지 않도록 함.
6. _layouts 폴더의 project.html 파일과 메인 폴더의 project.md, test-page.md 파일을 삭제함.
7. _data 폴더를 삭제함. 이 폴더에는 projects.yml이 들어있는데, 이 파일은 필요없기 때문임.

### ABOUT 수정
기존의 테마에서는 ABOUT에 자신을 설명하는 글과 더불어 CONTACT 버튼과 BLOG 버튼이 존재함.
CONTACT 버튼은 불필요하므로 이 버튼을 뺀다.
자신을 설명하는 글과 프로필 사진, 그리고 POST 내에서 본인의 이름을 클릭했을 시 연결되는 URL을 수정할 필요가 있음.
1. _includes 폴더의 blog.html 파일을 텍스트 편집기로 다음과 같이 수정.
2.  다음과 같은 코드를 지움으로써 ABOUT 페이지의 CONTACT 버튼을 삭제함.
``` 
    <div>
        <a href="{{site.url}}{{site.baseurl}}/#contact"
            class="button is-rounded is-uppercase has-text-weight-normal is-black is-outlined">Contact
            Me</a>
        </a>
    </div>
```
3. 메인 폴더의 _config.yml 파일에서 author-name과 author-image, author-url를 본인의 상황에 맞게 수정.

### footer 수정
기존의 테마에서의 footer는 MORE에 있는 Projects와 Test Page로 가는 링크가 존재함.
MORE에 있는 요소들은 불필요하므로 이 링크 섹션을 없앨 필요가 있음.
1. _includes 폴더의 footer.html 파일을 텍스트 편집기로 다음과 같이 수정.
2. 다음과 같은 코드를 지움으로써 footer에 더이상 불필요한 링크 섹션이 나타나지 않도록 함.
```
<!--Link Section-->
            <div class="column has-text-white">
                <h3>More Links</h3>
                {% for sitepage in site.html_pages offset: 4 %}
                {% unless sitepage.url == '/'  limit: 2 %}
                <li>
                    <a href="{{sitepage.url | absolute_url}}">{{sitepage.title}}</a>
                </li>
                {% endunless %}
                {% endfor %}
                <li>
                    <a target="_blank" href="{{site.url}}{{site.baseurl}}/feed.xml">Subscribe via RSS</a>
                </li>
            </div>
```

### 제목과 부제목 수정
메인 폴더의 _config.yml 파일에서 title과 description를 적절하게 수정함으로써 프로젝트에 맞는 제목과 부제목을 설정함.
