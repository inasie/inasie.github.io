---
title: github page 로 blog 만들기
date: 2018-11-30
last_modified_at: 2018-11-30
categories:
- IT일반
tags:
- 깃허브
- 블로그
- github
- github.io
- blog
- jekyll
---

오늘은 github의 page기능을 사용하여 blog를 만드는 방법을 알아보겠습니다.

> 이 포스팅은 jekyll theme를 검색 -> clone -> 커스터마이징하여 blog를 생성하는 방법을 설명합니다. <br>
clone없이 바로 사용하는 방법은 [이 포스트](https://inasie.github.io/it일반/jekyll-블로그-만들기)를 참고해주세요

## 1. Repository 생성

블로그로 사용할 repository를 생성합니다.

1. github 로그인
2. New repository
3. repository 이름 작성

> 이 repository 이름이 블로그 접속 URL을 결정하게 되므로 신중하게 결정합니다.<br>
예1) repository 이름이 {id}.github.io : https://{id}.github.io 로 접속 (예외적인 케이스)<br>
예2) repository 이름이 <span style="color:red">my-blog</span> : https://{id}.github.io/<span style="color:red">my-blog</span> 로 접속<br>
예3) repository 이름이 <span style="color:red">test</span> : https://{id}.github.io/<span style="color:red">test</span> 로 접속

저는 아파트 거래를 보여주는 블로그를 작성할 예정이므로 apt-deal-info 로 생성해보겠습니다.

빈 repository가 생성되었습니다.

![1](https://inasie.github.io/images/2018-11-30-github-blog-만들기/1.png)

## 2. Page 접속 설정

github page 기능을 사용하기 위해서는 repository 설정이 필요합니다.

> repository 이름이 {id}.github.io 로 만든 경우 예외적으로 page 설정이 자동으로 됩니다.

repostory Settings 메뉴에 들어갑니다.

![2](https://inasie.github.io/images/2018-11-30-github-blog-만들기/2.png)

Option항목의 하단부로 내려가면 GitHub Pages 항목이 있습니다.

Source 가 'None'으로 되어있는데 master branch로 변경해줍니다.
> master 브랜치의 코드 내용으로 page를 생성하겠다는 의미입니다.

그리고 Choose theme를 할 수 있는데, 저는 여기에 없는 다른 jekyll theme를 사용할 것이므로 무시하고 save를 누릅니다.

![3](https://inasie.github.io/images/2018-11-30-github-blog-만들기/3.png)

save를 누르고 나면 Github Pages항목에 'Your site is ready to be published at xxx' 문구가 생긴것을 볼 수 있습니다.<br>

![4](https://inasie.github.io/images/2018-11-30-github-blog-만들기/4.png)

아직 별다른 내용이 없기 때문에 링크를 들어가면 README.md에 작성된 내용이 보여집니다.

## 3. jekyll theme 선택

<http://jekyllthemes.org/> 에 방문하여 원하는 theme를 찾아봅니다.

오랜된 항목들도 있기 때문에 homepage가 없어졌거나 demo가 잘 나오지 않거나 license가 애매한 것들은 피해야합니다.

저는 [Jekyll-Uno](http://jekyllthemes.org/themes/jekyll-uno) 라는 theme가 맘에 들어 사용하기로 결정하였습니다.

theme를 결정하였으면 Homepage에 접속합니다.

![5](https://inasie.github.io/images/2018-11-30-github-blog-만들기/5.png)

그럼 위와같이 _includes, _layouts, _posts, ... 와 같이 repository가 구성되어 있는 것이 보입니다.

다른 jekyll 기반 페이지도 들어가보시면 비슷한 구성을 가지고 있습니다.

이 프로젝트를 clone 하여 수정하도록 하겠습니다. (fork를 해서 수정하셔도 되지만 이미 repository 구성을 하였고, git history를 가져오고 싶은 생각이 없어 그냥 clone해서 복사하여 쓰기로 합니다.)

```
git clone https://github.com/joshgerdes/jekyll-uno.git
```

내 repository에 복사해야 하기 때문에 위에서 만든 repoistory도 clone합니다.

```
git clone https://github.com/inasie/apt-deal-info.git
```

jekyll-uno의 파일들을 내 repo 에 복사합니다. (README.md 제외)

jekyll-uni의 경우 MIT라이센스이기 때문에 복사해서 수정/사용해도 문제가 없습니다.

## 4. jekyll page 구성

주요 폴더/파일의 용도를 알아봅니다.

|이름|용도|
|--|--|
|_includes|모든 파일들에서 참조 가능한 html파일들 위치|
|_layouts|주요 layout 구성(html 혹은 md)|
|_posts|블로그 글을 작성하는 폴더|
|_sass|스타일 설정|
|css|스타일 설정|
|fonts|기본 폰트 외 추가 폰트|
|images|image 파일들 위치|
|js|js파일들 모음|
|index.html|첫 페이지 구성|
|_config.yml|주요 설정|

## 5. Page 설정

_config.yml을 열어 Page의 주요 설정을 나에 맞게 수정합니다.

- title: 블로그 제목
- description : 블로그 설명
- <span style="color:red">**url**</span>: https://{id}.github.io 로 설정
- <span style="color:red">**baseurl**</span>: repostiory 이름으로 설정 (예외: repository이름이 {id}.github.io 인 경우 '/'로 설정)
- google_analytics: google 애널리틱스 설정 (추후 별도 포스팅 예정)
    - 접속자 정보를 파악하기 위한 설정
- disqus_shortname: discus 설정 (추후 별도 포스팅 예정)
    - 블로그에 댓글 기능 제공하기 위한 설정

```yml
# Site settings
title: 지역 별 아파트 실거래가 등록 정보
description: '오늘 등록된 아파트 실거래가 정보 제공'
url: 'https://inasie.github.io'
baseurl: '/apt-deal-info'
# google_analytics: 'UA-XXXXXX-X'
# disqus_shortname: 'your-disqus-name'

author:
  name: 'inasie'
  email: inasie@naver.com
  twitter_username:
  facebook_username:
  github_username: inasie
  linkedin_username:
```

수정된 내용을 push 합니다.

```git
git add -A
git commit -m "init blog"
git push
```

## 6. Blog 확인

https://{id}.github.io/{repostitory} 에 접속하여 blog가 제대로 보이는지 확인합니다.

![6](https://inasie.github.io/images/2018-11-30-github-blog-만들기/6.png)

제가 clone 한 jekyll-uno의 경우 _posts에 글 하나가 작성되어있어 blog를 눌러보면 해당 포스트가 보입니다.

## 7. 블로그 글 포스팅 해보기

블로그 글은 _posts에 작성하면 됩니다.

기존에 미리 작성되어있던 글들은 삭제하고 내 글을 올려봅니다.

_posts/ 폴더에 YYYY-MM-DD-{제목}.md 이름으로 파일을 생성합니다.


```
_posts/2018-11-30-블로그-첫-글.md
```

그리고 블로그 글 상단에 아래와 같은 포멧으로 정보를 작성해줍니다.

```md
---
title:  "블로그 첫 글"
date: 2018-11-30
categories: ['일반']
tags: ['블로그', 'jekyll', 'github', 'github.io']
---
```

> <span style="color:red">**주의**</span> 파일이름 규칙이 맞지 않거나 상단 포멧이 제대로 인식되지 않으면 블로그 포스팅이 되지 않습니다.

그리고 아래쪽에 실제 블로그 내용을 markdown 문법으로 작성해줍니다.

```md
## 블로그가 완성되었습니다.
```

내용을 저장하고 push 합니다.

```bash
git add -A
git commmit -m "add a post"
git push
```

다시 블로그 페이지를 들어가 새로 고침하여 포스팅이 잘 되었는지 확인해봅니다.

> 글을 등록하면 실제 웹 페이지에 반영되기까지 시간이 조금 걸립니다. 바로 변경되지 않는다면 조금 더 기다려보세요.

> 글 포멧이 잘못되어 페이지 생성 시 에러가 난 경우 에러 내용에 대한 메일이 날라옵니다.

![7](https://inasie.github.io/images/2018-11-30-github-blog-만들기/7.png)

## 8. 결론

지금까지 github page에 jekyll theme를 이용한 블로그를 만드는 방법을 알아보았습니다.

물론 이렇게 복잡한 방법보다 네이버/티스토리 등을 사용하는 것이 훨씬 간단합니다. <br>
하지만 여러가지 이유로 github 페이지를 이용하고자 하는 요구사항이 있을 것으로 생각됩니다. <br>
저의 경우 마크다운 문법을 지원한다는 것과 블로그 포스팅 개수 제한이 없어 봇으로 포스팅이 가능한 점 때문에 사용하게 되었습니다.

이 글을 보시는 분들도 참고하셔서 멋진 블로그 생활 하시길 바랍니다.

---

이 글에서 사용한 repository 보기 : <https://github.com/inasie/apt-deal-info>

이 글에서 작성한 blog 보기 : <https://inasie.github.io/apt-deal-info>