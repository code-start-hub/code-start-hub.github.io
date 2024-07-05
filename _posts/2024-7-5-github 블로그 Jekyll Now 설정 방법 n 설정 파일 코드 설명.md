---
layout: post
title: github 블로그 Jekyll Now 설정 방법 n 설정 파일 코드 설명
render_with_liquid: false
---

Jekyll Now는 Jekyll 블로그를 간편하게 시작할 수 있도록 돕는 템플릿입니다. 명령어를 거의 사용하지 않고도 GitHub Pages에 블로그를 호스팅할 수 있습니다. 아래는 Jekyll Now를 설정하는 방법을 단계별로 설명한 것입니다:

1. **Repository 포크하기**:
    - 먼저 [Jekyll Now GitHub 저장소](https://github.com/barryclark/jekyll-now)를 포크합니다.
2. **Repository 이름 변경**:
    - 포크한 저장소의 이름을 `username.github.io`로 변경합니다. 여기서 `username`은 GitHub 사용자명을 의미합니다. 이렇게 하면 GitHub Pages가 이 저장소를 블로그 사이트로 인식합니다.
3. **GitHub Pages 활성화**:
    - GitHub 저장소 설정(Settings)에서 Pages 섹션을 찾아 배포(Deploy) 옵션을 설정합니다. 주로 `main` 브랜치를 선택하여 GitHub Pages가 사이트를 빌드하도록 합니다.
4. **개인화**:
    - `_config.yml` 파일을 수정하여 블로그 설정을 개인화합니다. 여기서 사이트 제목, 설명, 이메일, 소셜 미디어 링크 등을 설정할 수 있습니다. 코드 에디터를 사용하여 직접 수정을 수행하거나 브라우저 내에서 할 수 있습니다[0].
5. **포스트 작성**:
    - `_posts` 폴더에는 Markdown 형식의 파일을 추가하여 새 블로그 게시물을 작성합니다. 파일 이름은 `YYYY-MM-DD-포스트-제목.md` 형식으로 지정해야 합니다. 예를 들어, `2024-07-04-my-first-post.md`처럼 파일을 작성합니다.
6. **추가 기능 설정**:
    - 필요에 따라 댓글 서비스(예: Disqus)를 연동하거나[5][6], 태그 기능을 추가할 수 있습니다[1]. 각 기능의 설정 방법은 공식 문서나 관련 블로그 포스트를 참고하여 설정할 수 있습니다.

#### 예제: `_config.yml` 파일 설정

```yaml
title: 나의 블로그
email: me@example.com
description: >-
  이것은 나의 멋진 블로그입니다.
baseurl: "" # the subpath of your site, e.g. /blog
url: "<https://username.github.io>" # the base hostname & protocol for your site
twitter_username: your_twitter
github_username:  your_github
```

이 단계를 따르면 Jekyll Now를 이용하여 개인 블로그를 쉽고 빠르게 설정할 수 있습니다. Markdown 파일을 이용하여 게시물을 추가하고, 사이트 설정을 수정하여 개성을 더할 수 있습니다.

## 설정 파일 설명 및 코드를 학습하고 적용하는 방법

### 디렉토리 구조

<img src="https://drive.google.com/uc?export=view&id=1tGRs_CBrt9f26-S797kNZBxSQ2CmJC70" width="300" alt="Jekyll-now_directory-tree">

## 1) config 파일 (YAML)

### **_config.yml**

- **주석 포함 YAML Code**
    
    ```yaml
    # 이 파일은 사이트를 커스터마이즈하기 위한 구성 플래그들을 포함합니다.
    # Configuration file for customizing your site
    
    # 사이트 이름 (헤더에 표시됩니다)
    name: Your Name # 사이트의 이름입니다. 헤더에 표시됩니다.
    
    # 짧은 바이오 또는 설명 (헤더에 표시됩니다)
    description: Web Developer from Somewhere # 사이트의 짧은 설명입니다. 헤더에 표시됩니다.
    
    # 아바타 또는 프로필 사진의 URL (GitHub 프로필 사진을 사용할 수 있습니다)
    avatar: <https://raw.githubusercontent.com/barryclark/jekyll-now/master/images/jekyll-logo.png> # 프로필 사진의 URL입니다.
    
    # 아래의 플래그들은 선택 사항입니다.
    # The following flags are optional
    
    # 입력한 사용자 이름에 따라 푸터에 아이콘을 포함합니다
    footer-links:
      dribbble: # 드리블 사용자 이름입니다.
      email: # 이메일 주소입니다.
      facebook: # 페이스북 사용자 이름입니다.
      flickr: # 플리커 사용자 이름입니다.
      github: barryclark/jekyll-now # GitHub 사용자 이름 또는 저장소입니다.
      instagram: # 인스타그램 사용자 이름입니다.
      linkedin: # 링크드인 사용자 이름입니다.
      pinterest: # 핀터레스트 사용자 이름입니다.
      rss: # RSS 아이콘을 활성화하려면 여기에 아무 내용이나 입력하세요.
      twitter: jekyllrb # 트위터 사용자 이름입니다.
      stackoverflow: # 스택오버플로우 프로필, 예: "users/50476/bart-kiers"
      youtube: # 유튜브 채널 또는 사용자 이름입니다.
      googleplus: # 프로필 URL에 있는 plus.google.com/ 이후의 내용입니다.
    
    # 게시물에 댓글을 달 수 있도록 디스커스 단축 이름을 입력하세요
    # 디스커스 계정의 설정 페이지에서 단축 이름을 찾을 수 있습니다.
    disqus: # 디스커스 단축 이름을 입력하세요.
    
    # Google Analytics 웹 추적 코드를 입력하세요 (예: UA-2110908-2) 추적을 활성화합니다.
    google_analytics: # Google Analytics 웹 추적 코드를 입력하세요.
    
    # 웹사이트 URL을 입력하세요 (예: <http://barryclark.github.io> 또는 <http://www.barryclark.co>)
    # Sitemap.xml과 RSS 피드를 위해 사용됩니다.
    url: # 웹사이트 URL을 입력하세요.
    
    # 사이트를 GitHub 페이지의 프로젝트 저장소에 호스팅하는 경우
    # (<http://yourusername.github.io/repository-name>)
    # 사용자 저장소가 아닌 경우 (<http://yourusername.github.io>)
    # 여기에 baseurl을 추가하세요, 예: "/repository-name"
    baseurl: "" # GitHub 페이지 프로젝트 저장소의 baseurl을 입력하세요.
    
    # 아래의 구성 플래그는 변경할 필요가 없습니다.
    # No need to change any of the configuration flags below
    
    permalink: /:title/ # 페이지 URL 구조를 설정합니다.
    
    # 사용 중인 Jekyll Now 버전
    version: v1.2.0 # Jekyll Now의 버전입니다.
    
    # Jekyll 3는 이제 Markdown을 위해 Kramdown만 지원합니다.
    kramdown:
      # GitHub 스타일의 마크다운을 사용하며, 세 개의 백틱으로 감싸진 코드 블록 포함
      input: GFM # GitHub 스타일 마크다운(GFM)을 사용합니다.
      # Jekyll 3와 GitHub Pages는 이제 구문 강조를 위해 Rouge만 지원합니다.
      syntax_highlighter: rouge # 구문 강조를 위해 Rouge를 사용합니다.
      syntax_highlighter_opts:
        # 기존의 Pygments 구문 강조 CSS를 사용합니다.
        css_class: 'highlight' # 구문 강조 CSS 클래스입니다.
    
    # Sass 파셜 디렉토리를 설정합니다. 우리는 @import를 사용합니다.
    sass:
      style: :expanded # :compressed 대신 :expanded 스타일을 사용할 수도 있습니다. (압축을 원하면 :compressed를 사용하세요.)
    
    # 다음 플러그인을 사용합니다.
    gems:
      - jekyll-sitemap # 공식 Jekyll 사이트맵 젬을 사용하여 사이트맵을 생성합니다.
      - jekyll-feed # 공식 Jekyll 피드 젬을 사용하여 Atom 피드를 생성합니다.
    
    # 다음 파일들을 프로덕션 _site에서 제외합니다.
    exclude:
      - Gemfile # Gemfile을 제외합니다.
      - Gemfile.lock # Gemfile.lock을 제외합니다.
      - LICENSE # LICENSE 파일을 제외합니다.
      - README.md # README.md 파일을 제외합니다.
      - CNAME # CNAME 파일을 제외합니다.
    
    ```
    
- **설명**
    
    이 YAML 파일은 Jekyll 기반 블로그의 설정 파일입니다. 이 파일을 통해 블로그의 다양한 설정을 할 수 있습니다. 각 항목은 블로그의 특정 요소를 설정하거나 커스터마이즈하는 데 사용됩니다.
    
- **주요 용어**
    - **name**: 블로그의 이름입니다. 헤더에 표시됩니다.
    - **description**: 블로그의 설명입니다. 헤더에 표시됩니다.
    - **avatar**: 프로필 사진의 URL입니다. 헤더에 표시됩니다.
    - **footer-links**: 푸터에 표시할 소셜 미디어 링크 목록입니다.
    - **disqus**: 디스커스 댓글 시스템을 활성화하기 위한 단축 이름입니다.
    - **google_analytics**: Google Analytics 추적 코드를 입력하여 웹사이트 트래픽을 추적할 수 있습니다.
    - **url**: 웹사이트의 기본 URL입니다.
    - **baseurl**: GitHub Pages 프로젝트 저장소를 위한 URL 경로입니다.
    - **permalink**: 블로그 포스트의 URL 구조를 설정합니다.
    - **version**: 사용 중인 Jekyll Now의 버전입니다.
    - **kramdown**: Jekyll에서 지원하는 Markdown 파서입니다.
    - **sass**: CSS 전처리기인 Sass의 설정입니다.
    - **gems**: Jekyll 플러그인의 목록입니다.
    - **exclude**: 프로덕션 사이트에서 제외할 파일 목록입니다.
- **사용 방법**
    1. **블로그 이름과 설명 설정**: `name`과 `description` 필드를 사용하여 블로그의 이름과 설명을 설정합니다.
    2. **프로필 사진 추가**: `avatar` 필드에 프로필 사진의 URL을 입력합니다.
    3. **소셜 미디어 링크 설정**: `footer-links` 섹션에서 원하는 소셜 미디어 계정 정보를 입력합니다.
    4. **디스커스 및 Google Analytics 설정**: `disqus`와 `google_analytics` 필드를 사용하여 해당 서비스를 설정합니다.
    5. **기본 URL 설정**: `url` 필드에 블로그의 기본 URL을 입력합니다.
    6. **Jekyll 플러그인 추가**: `gems` 섹션에 필요한 플러그인을 추가합니다.
- **주의사항**
    - YAML은 들여쓰기로 구조를 나타내므로 정확한 들여쓰기를 유지해야 합니다.
    - URL과 같은 필드는 정확하게 입력해야 웹사이트가 올바르게 작동합니다.
    - 필드를 빈 상태로 두면 해당 기능이 비활성화될 수 있습니다.
- **확장방법**
    - 추가 플러그인을 설치하여 블로그 기능을 확장할 수 있습니다. 예: SEO, 이미지 최적화 플러그인 등.
    - `footer-links`에 더 많은 소셜 미디어 링크를 추가할 수 있습니다.
    - 블로그 테마를 커스터마이즈하여 더 독특한 디자인을 적용할 수 있습니다.
    - 추가 구성 파일을 작성하여 여러 환경(개발, 테스트, 운영)에 대한 설정을 관리할 수 있습니다.

## 2) html 파일

- **index.html**
    - **HTML Code** with Comments
        
        ```html
        ---
        layout: default
        ---
        
        <!-- 포스트 목록을 표시할 div 요소 -->
        <div class="posts">
          <!-- Jekyll 템플릿 언어를 사용하여 사이트의 모든 포스트를 반복합니다 -->
          {% for post in site.posts %}
            <!-- 각 포스트를 나타내는 article 요소 -->
            <article class="post">
              <!-- 포스트 제목을 링크로 감싸서 표시합니다 -->
              <h1><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h1>
              <!-- 포스트의 요약을 표시하는 div 요소 -->
              <div class="entry">
                {{ post.excerpt }}
              </div>
              <!-- 'Read More' 링크를 제공하여 전체 포스트로 이동합니다 -->
              <a href="{{ site.baseurl }}{{ post.url }}" class="read-more">Read More</a>
            </article>
          {% endfor %}
        </div>
        
        ```
        
    - **Explanation**
        
        이 HTML 파일은 Jekyll 사이트에서 모든 블로그 포스트를 목록으로 표시하는 기능을 담당합니다. Jekyll은 정적 사이트 생성기로, 주로 블로그와 같은 콘텐츠 중심의 웹사이트를 생성하는 데 사용됩니다.
        
    - **Key Terms**
        - **`<div>`**: HTML의 블록 요소로, 컨테이너 역할을 하여 다른 요소들을 그룹화합니다.
        {% raw %}
        - **`{% for post in site.posts %}`**: Jekyll 템플릿 언어인 Liquid의 구문으로, 사이트의 모든 포스트를 반복 처리합니다.
        {% endraw %}
        - **`<article>`**: 독립적으로 구분할 수 있는 콘텐츠 블록을 나타내는 HTML5 요소입니다.
        - **`<h1>`**: HTML에서 가장 중요한 제목을 나타냅니다.
        - **`<a>`**: 하이퍼링크를 생성하는 HTML 요소입니다.
        - **`{{ }}`**: Liquid 템플릿 언어에서 변수나 데이터를 출력할 때 사용합니다.
        - **`post.url`**: 각 포스트의 URL을 나타내는 Jekyll 변수입니다.
        - **`post.title`**: 각 포스트의 제목을 나타내는 Jekyll 변수입니다.
        - **`post.excerpt`**: 각 포스트의 요약을 나타내는 Jekyll 변수입니다.
    - **Usage**
        1. **블로그 포스트 목록 생성**: Jekyll을 사용하여 사이트의 모든 블로그 포스트를 반복하고 각 포스트의 제목과 요약을 표시합니다.
        2. **포스트 제목 링크**: 포스트 제목을 클릭하면 해당 포스트의 전체 내용을 볼 수 있는 페이지로 이동합니다.
        3. **요약 및 'Read More' 링크**: 각 포스트의 요약을 표시하고, 'Read More' 링크를 클릭하면 전체 포스트 페이지로 이동합니다.
    - **Important Points**
        - Jekyll의 Liquid 템플릿 언어를 사용할 때 구문 오류가 없도록 주의하세요.
        - HTML 태그를 올바르게 닫아야 페이지가 올바르게 렌더링됩니다.
        - 사이트의 구조와 스타일을 유지하기 위해 CSS 클래스(`class="posts"`, `class="post"`, `class="read-more"`)를 사용하여 스타일을 정의할 수 있습니다.
    - **Extensions**
        - **추가 정보 표시**: 각 포스트에 날짜, 저자 이름, 카테고리 등 추가 정보를 표시할 수 있습니다.
            
            ```html
            <p class="post-meta">{{ post.date | date: "%B %d, %Y" }} by {{ post.author }}</p>
            ```
            
        - **포스트 필터링**: 특정 카테고리나 태그에 따라 포스트를 필터링하여 표시할 수 있습니다.
            
            ```html
            {% raw %}
            {% for post in site.posts %}
              {% if post.category == "tech" %}
                <!-- 포스트 내용 -->
              {% endif %}
            {% endfor %}
            {% endraw %}
            ```
            
        - **스타일 개선**: CSS를 사용하여 포스트 목록의 스타일을 개선할 수 있습니다. 예를 들어, 포스트 제목의 색상이나 크기를 변경할 수 있습니다.
            
            ```css
            .post h1 {
              color: #333;
              font-size: 24px;
            }
            ```
            
        
        이 HTML 코드는 기본적인 블로그 포스트 목록을 생성하는 예제입니다. Jekyll과 Liquid 템플릿 언어의 기본 개념을 이해하고 이를 확장하여 더 복잡하고 다양한 기능을 구현할 수 있습니다.
        

### _layouts 디렉토리

- **default.html**
    - **HTML Code** with Comments
        
        ```html
        <!DOCTYPE html> <!-- HTML 문서의 유형을 선언합니다. -->
        {% raw %}
        <html> <!-- HTML 문서의 시작을 알립니다. -->
          <head> <!-- 문서의 머리말로, 메타데이터를 포함합니다. -->
            <!-- 페이지 제목을 설정합니다. 페이지에 제목이 있는 경우 그 제목을 사용하고, 사이트 이름과 설명을 추가합니다. -->
            <title>{% if page.title %}{{ page.title }} – {{ site.name }} – {{ site.description }}</title>
        
            <!-- meta.html 파일을 포함하여 메타데이터를 설정합니다. -->
            {% include meta.html %}
        
            <!-- Internet Explorer 9 이하 버전에서 HTML5 요소를 지원하도록 하는 스크립트입니다. -->
            <!--[if lt IE 9]>
              <script src="<http://html5shiv.googlecode.com/svn/trunk/html5.js>"></script>
            <![endif]-->
        
            <!-- CSS 파일을 연결합니다. 사이트의 기본 스타일시트입니다. -->
            <link rel="stylesheet" type="text/css" href="{{ site.baseurl }}/style.css" />
            <!-- RSS 피드 링크를 설정합니다. -->
            <link rel="alternate" type="application/rss+xml" title="{{ site.name }} - {{ site.description }}" href="{{ site.baseurl }}/feed.xml" />
        
            <!-- Jekyll Now를 사용하여 생성되었음을 알리는 주석입니다. -->
            <!-- Created with Jekyll Now - <http://github.com/barryclark/jekyll-now> -->
          </head>
        
          <body> <!-- 문서의 본문을 시작합니다. -->
            <!-- 헤더 영역을 나타내는 div 요소입니다. -->
            <div class="wrapper-masthead">
              <div class="container">
                <!-- 웹사이트의 헤더를 나타내는 요소입니다. -->
                <header class="masthead clearfix">
                  <!-- 사이트의 아바타(프로필 이미지)를 링크로 설정합니다. -->
                  <a href="{{ site.baseurl }}/" class="site-avatar"><img src="{{ site.avatar }}" /></a>
        
                  <!-- 사이트 정보를 담는 div 요소입니다. -->
                  <div class="site-info">
                    <!-- 사이트 이름을 나타내는 h1 요소입니다. -->
                    <h1 class="site-name"><a href="{{ site.baseurl }}/">{{ site.name }}</a></h1>
                    <!-- 사이트 설명을 나타내는 p 요소입니다. -->
                    <p class="site-description">{{ site.description }}</p>
                  </div>
        
                  <!-- 내비게이션 메뉴를 나타내는 nav 요소입니다. -->
                  <nav>
                    <a href="{{ site.baseurl }}/">Blog</a> <!-- 블로그 페이지 링크 -->
                    <a href="{{ site.baseurl }}/about">About</a> <!-- About 페이지 링크 -->
                  </nav>
                </header>
              </div>
            </div>
        
            <!-- 메인 콘텐츠를 담는 div 요소입니다. -->
            <div id="main" role="main" class="container">
              {{ content }} <!-- 페이지의 주요 콘텐츠가 표시되는 자리입니다. -->
            </div>
        
            <!-- 푸터 영역을 나타내는 div 요소입니다. -->
            <div class="wrapper-footer">
              <div class="container">
                <!-- 웹사이트의 푸터를 나타내는 요소입니다. -->
                <footer class="footer">
                  <!-- svg-icons.html 파일을 포함하여 SVG 아이콘을 사용합니다. -->
                  {% include svg-icons.html %}
                </footer>
              </div>
            </div>
        
            <!-- analytics.html 파일을 포함하여 Google Analytics 코드를 추가합니다. -->
            {% include analytics.html %}
          </body>
        </html> <!-- HTML 문서의 끝을 알립니다. -->
        {% endraw %}
        ```
        
    - Explanation
        
        이 HTML 파일은 Jekyll 사이트의 기본 레이아웃 파일입니다. Jekyll은 정적 사이트 생성기로, 주로 블로그와 같은 콘텐츠 중심의 웹사이트를 생성하는 데 사용됩니다. 이 파일은 웹사이트의 공통 레이아웃을 정의합니다.
        
    - Key Terms
        - **`<!DOCTYPE html>`**: HTML 문서의 유형을 선언하여 브라우저가 HTML5 표준을 따르도록 합니다.
        - **`<html>`**: HTML 문서의 루트 요소로, 모든 HTML 콘텐츠를 포함합니다.
        - **`<head>`**: 메타데이터, 스타일, 스크립트 등을 포함하는 HTML 문서의 머리 부분입니다.
        - **`<title>`**: 브라우저 탭에 표시될 문서의 제목을 정의합니다.
        - **`{% include %}`**: Jekyll 템플릿 언어에서 다른 파일을 포함하는 구문입니다.
        - **`<!--[if lt IE 9]> ... <![endif]-->`**: 조건부 주석으로, 특정 버전의 Internet Explorer에서만 실행되는 내용을 포함합니다.
        - **`<link>`**: 외부 CSS 파일이나 다른 리소스를 문서에 연결합니다.
        - **`<body>`**: HTML 문서의 본문으로, 사용자에게 표시되는 모든 콘텐츠를 포함합니다.
        - **`<div>`**: HTML의 블록 요소로, 다른 요소들을 그룹화합니다.
        - **`<header>`**: 문서나 섹션의 머리말을 나타내는 HTML5 요소입니다.
        - **`<nav>`**: 내비게이션 링크를 포함하는 HTML5 요소입니다.
        - **`<h1>`**: 가장 중요한 제목을 나타내는 HTML 요소입니다.
        - **`<p>`**: 단락을 나타내는 HTML 요소입니다.
        - **`<footer>`**: 문서나 섹션의 바닥글을 나타내는 HTML5 요소입니다.
    - Usage
        1. **페이지 제목 설정**: `<title>` 태그는 페이지 제목을 설정하며, 이 제목은 브라우저 탭에 표시됩니다.
        2. **CSS 및 메타데이터 포함**: `<link>` 태그와 `{% include meta.html %}` 구문을 사용하여 스타일시트와 메타데이터를 포함합니다.
        3. **헤더 설정**: `<header>` 요소 안에 사이트 이름, 설명, 내비게이션 링크를 포함합니다.
        4. **메인 콘텐츠 표시**: `<div id="main">` 요소는 페이지의 주요 콘텐츠를 포함합니다.
        5. **푸터 설정**: `<footer>` 요소는 사이트의 푸터를 설정하며, SVG 아이콘을 포함합니다.
    - **Important Points**
        - HTML 태그를 올바르게 닫아야 페이지가 올바르게 렌더링됩니다.
        - CSS 파일 경로와 같은 URL이 정확한지 확인하세요.
        - Jekyll의 Liquid 템플릿 언어를 사용할 때 구문 오류가 없도록 주의하세요.
        - 조건부 주석은 Internet Explorer의 특정 버전에서만 작동하므로 다른 브라우저에서는 무시됩니다.
    - **Extensions**
        - **추가 페이지 링크**: 내비게이션 메뉴에 더 많은 페이지 링크를 추가할 수 있습니다.
            
            ```html
            <nav>
              <a href="{{ site.baseurl }}/">Blog</a>
              <a href="{{ site.baseurl }}/about">About</a>
              <a href="{{ site.baseurl }}/contact">Contact</a>
            </nav>
            ```
            
        - **스타일 개선**: CSS를 사용하여 사이트의 디자인을 개선할 수 있습니다. 예를 들어, 헤더와 푸터의 배경색을 변경할 수 있습니다.
            
            ```css
            .masthead {
              background-color: #f8f9fa;
            }
            .footer {
              background-color: #343a40;
              color: white;
            }
            ```
            
        - **추가 메타태그**: SEO를 개선하기 위해 추가 메타태그를 포함할 수 있습니다.
            
            ```html
            <meta name="description" content="A blog about web development">
            <meta name="keywords" content="HTML, CSS, JavaScript, Jekyll">
            ```
            
        - **JavaScript 추가**: 사용자 인터랙션을 위해 JavaScript 파일을 포함할 수 있습니다.
            
            ```html
            <script src="{{ site.baseurl }}/scripts.js"></script>
            ```
            
        
        이 HTML 코드는 기본적인 웹사이트 레이아웃을 생성하는 예제입니다. Jekyll과 Liquid 템플릿 언어의 기본 개념을 이해하고 이를 확장하여 더 복잡하고 다양한 기능을 구현할 수 있습니다.
        
- **page.html**
    - **HTML Code** with Comments
        
        ```html
        ---
        layout: default
        ---
        <!-- Jekyll 템플릿에서 상위 레이아웃으로 'default'를 사용함을 선언합니다 -->
        
        <!-- 페이지 콘텐츠를 담는 article 요소 -->
        <article class="page">
          <!-- 페이지의 제목을 표시하는 h1 요소 -->
          <h1>{{ page.title }}</h1> <!-- Jekyll 변수를 사용하여 페이지 제목을 출력합니다 -->
        
          <!-- 페이지의 본문 내용을 담는 div 요소 -->
          <div class="entry">
            {{ content }} <!-- Jekyll 변수를 사용하여 페이지 콘텐츠를 출력합니다 -->
          </div>
        </article>
        
        ```
        
    - Explanation
        
        이 HTML 파일은 Jekyll 사이트의 페이지 레이아웃 파일입니다. Jekyll은 정적 사이트 생성기로, 주로 블로그와 같은 콘텐츠 중심의 웹사이트를 생성하는 데 사용됩니다. 이 레이아웃 파일은 각각의 페이지에 공통으로 사용될 구조를 정의합니다.
        
    - Key Terms
        - **`--`**: Jekyll의 프론트 매터(Front Matter) 블록을 시작하고 끝내는 구분자입니다. 이 블록 내에서는 YAML 형식으로 메타데이터를 정의합니다.
        - **`layout`**: 상위 레이아웃을 지정하는 프론트 매터 속성입니다. 여기서는 'default' 레이아웃을 사용합니다.
        - **`<article>`**: 독립적인 콘텐츠 블록을 나타내는 HTML5 요소입니다.
        - **`<h1>`**: 가장 중요한 제목을 나타내는 HTML 요소입니다.
        - **`{{ }}`**: Jekyll 템플릿 언어인 Liquid의 구문으로, 변수를 출력할 때 사용됩니다.
        - **`page.title`**: Jekyll 변수로, 현재 페이지의 제목을 나타냅니다.
        - **`content`**: Jekyll 변수로, 현재 페이지의 주요 콘텐츠를 나타냅니다.
    - Usage
        1. **상위 레이아웃 지정**: `layout: default`로 상위 레이아웃 파일을 지정합니다. 상위 레이아웃은 `_layouts/default.html` 파일입니다.
        2. **페이지 제목 출력**: `<h1>{{ page.title }}</h1>`는 현재 페이지의 제목을 출력합니다.
        3. **페이지 콘텐츠 출력**: `<div class="entry">{{ content }}</div>`는 현재 페이지의 주요 콘텐츠를 출력합니다.
    - **Important Points**
        - HTML 태그를 올바르게 닫아야 페이지가 올바르게 렌더링됩니다.
        - Jekyll의 Liquid 템플릿 언어를 사용할 때 구문 오류가 없도록 주의하세요.
        - 레이아웃 파일을 수정할 때, 다른 페이지에도 영향을 미칠 수 있으므로 주의해야 합니다.
    - **Extensions**
        - **추가 스타일 적용**: CSS를 사용하여 `article`, `h1`, `div.entry` 요소에 스타일을 적용할 수 있습니다.
            
            ```css
            .page {
              max-width: 800px;
              margin: 0 auto;
              padding: 20px;
            }
            .page h1 {
              font-size: 2em;
              margin-bottom: 20px;
            }
            .entry {
              font-size: 1.2em;
              line-height: 1.6;
            }
            ```
            
        - **메타데이터 추가**: 페이지의 메타데이터를 프론트 매터에 추가하여 다양한 정보를 포함할 수 있습니다.
            
            ```yaml
            ---
            layout: default
            title: My Page Title
            description: A brief description of my page.
            ---
            ```
            
        - **추가 섹션 추가**: 페이지 레이아웃에 추가 섹션을 포함하여 더 많은 콘텐츠를 구조화할 수 있습니다.
            
            ```html
            <article class="page">
              <h1>{{ page.title }}</h1>
              <div class="entry">
                {{ content }}
              </div>
              <div class="additional-info">
                <h2>Additional Information</h2>
                <p>Some extra details about the page content.</p>
              </div>
            </article>
            ```
            
        
        이 HTML 코드는 Jekyll 기반 웹사이트에서 페이지의 기본 레이아웃을 정의하는 예제입니다. Jekyll과 Liquid 템플릿 언어의 기본 개념을 이해하고 이를 확장하여 더 복잡하고 다양한 기능을 구현할 수 있습니다.
        
- **post.html**
    - **HTML Code** with Comments
        
        ```html
        ---
        layout: default
        ---
        <!-- 이 파일은 'default' 레이아웃을 상속받는 Jekyll 템플릿입니다 -->
        
        <!-- 블로그 포스트를 나타내는 article 요소 -->
        <article class="post">
          <!-- 포스트 제목을 표시하는 h1 요소 -->
          <h1>{{ page.title }}</h1> <!-- Jekyll 변수를 사용하여 포스트 제목을 출력합니다 -->
        
          <!-- 포스트 본문 내용을 담는 div 요소 -->
          <div class="entry">
            {{ content }} <!-- Jekyll 변수를 사용하여 포스트 콘텐츠를 출력합니다 -->
          </div>
        
          <!-- 포스트 작성 날짜를 표시하는 div 요소 -->
          <div class="date">
            Written on {{ page.date | date: "%B %e, %Y" }} <!-- Jekyll 변수를 사용하여 포스트 작성 날짜를 지정된 형식으로 출력합니다 -->
          </div>
        
          <!-- Disqus 댓글 시스템을 포함하는 부분입니다 -->
          {% include disqus.html %} <!-- disqus.html 파일을 포함하여 Disqus 댓글 기능을 추가합니다 -->
        </article>
        
        ```
        
    - Explanation
        
        이 HTML 파일은 Jekyll 블로그 사이트의 개별 블로그 포스트 레이아웃 파일입니다. Jekyll은 정적 사이트 생성기로, 주로 블로그와 같은 콘텐츠 중심의 웹사이트를 생성하는 데 사용됩니다. 이 레이아웃 파일은 각 블로그 포스트 페이지에 공통으로 사용될 구조를 정의합니다.
        
    - Key Terms
        - **`--`**: Jekyll의 프론트 매터(Front Matter) 블록을 시작하고 끝내는 구분자입니다. 이 블록 내에서는 YAML 형식으로 메타데이터를 정의합니다.
        - **`layout`**: 상위 레이아웃을 지정하는 프론트 매터 속성입니다. 여기서는 'default' 레이아웃을 사용합니다.
        - **`<article>`**: 독립적인 콘텐츠 블록을 나타내는 HTML5 요소입니다. 여기서는 블로그 포스트를 의미합니다.
        - **`<h1>`**: 가장 중요한 제목을 나타내는 HTML 요소입니다.
        - **`<div>`**: HTML의 블록 요소로, 다른 요소들을 그룹화합니다.
        - **`{{ }}`**: Jekyll 템플릿 언어인 Liquid의 구문으로, 변수를 출력할 때 사용됩니다.
        - **`page.title`**: Jekyll 변수로, 현재 페이지의 제목을 나타냅니다.
        - **`content`**: Jekyll 변수로, 현재 페이지의 주요 콘텐츠를 나타냅니다.
        - **`page.date`**: Jekyll 변수로, 현재 페이지의 작성 날짜를 나타냅니다.
        - **`{% include %}`**: Jekyll 템플릿 언어에서 다른 파일을 포함하는 구문입니다.
    - Usage
        1. **상위 레이아웃 지정**: `layout: default`로 상위 레이아웃 파일을 지정합니다. 상위 레이아웃은 `_layouts/default.html` 파일입니다.
        2. **포스트 제목 출력**: `<h1>{{ page.title }}</h1>`는 현재 포스트의 제목을 출력합니다.
        3. **포스트 콘텐츠 출력**: `<div class="entry">{{ content }}</div>`는 현재 포스트의 주요 콘텐츠를 출력합니다.
        4. **작성 날짜 출력**: `<div class="date">Written on {{ page.date | date: "%B %e, %Y" }}</div>`는 포스트 작성 날짜를 출력합니다.
        5. **Disqus 댓글 포함**: `{% include disqus.html %}`는 Disqus 댓글 시스템을 포함합니다.
    - **Important Points**
        - HTML 태그를 올바르게 닫아야 페이지가 올바르게 렌더링됩니다.
        - Jekyll의 Liquid 템플릿 언어를 사용할 때 구문 오류가 없도록 주의하세요.
        - 레이아웃 파일을 수정할 때, 다른 포스트 페이지에도 영향을 미칠 수 있으므로 주의해야 합니다.
    - **Extensions**
        - **추가 정보 표시**: 포스트에 작성자 이름이나 카테고리와 같은 추가 정보를 표시할 수 있습니다.
            
            ```html
            <div class="author">
              Written by {{ page.author }}
            </div>
            <div class="category">
              Category: {{ page.category }}
            </div>
            ```
            
        - **스타일 개선**: CSS를 사용하여 포스트 레이아웃의 디자인을 개선할 수 있습니다.
            
            ```css
            .post {
              max-width: 800px;
              margin: 0 auto;
              padding: 20px;
            }
            .post h1 {
              font-size: 2.5em;
              margin-bottom: 20px;
            }
            .entry {
              font-size: 1.2em;
              line-height: 1.6;
            }
            .date {
              font-size: 0.9em;
              color: gray;
            }
            ```
            
        - **메타데이터 추가**: SEO를 개선하기 위해 메타데이터를 프론트 매터에 추가하여 다양한 정보를 포함할 수 있습니다.
            
            ```yaml
            ---
            layout: post
            title: My Post Title
            author: John Doe
            date: 2023-07-03
            category: Blog
            description: A brief description of my post.
            ---
            ```
            
        - **추가 섹션 추가**: 포스트 레이아웃에 추가 섹션을 포함하여 더 많은 콘텐츠를 구조화할 수 있습니다.
            
            ```html
            <article class="post">
              <h1>{{ page.title }}</h1>
              <div class="entry">
                {{ content }}
              </div>
              <div class="date">
                Written on {{ page.date | date: "%B %e, %Y" }}
              </div>
              <div class="tags">
                Tags: {{ page.tags | join: ", " }}
              </div>
              {% include disqus.html %}
            </article>
            ```
            
        
        이 HTML 코드는 Jekyll 기반 웹사이트에서 블로그 포스트의 기본 레이아웃을 정의하는 예제입니다. Jekyll과 Liquid 템플릿 언어의 기본 개념을 이해하고 이를 확장하여 더 복잡하고 다양한 기능을 구현할 수 있습니다.
        

### _includes 디렉토리

- **analytics.html**
    - **HTML Code** with Comments
        
        ```html
        {% raw %}
        {% if site.google_analytics %}
        	<!-- Google Analytics를 설정합니다 -->
        	<script>
        		(function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
        		(i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
        		m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
        		})(window,document,'script','//www.google-analytics.com/analytics.js','ga');
        
        		ga('create', '{{ site.google_analytics }}', 'auto'); <!-- Google Analytics 트래킹 ID를 사용하여 추적기 생성 -->
        		ga('send', 'pageview', {
        		  'page': '{{ site.baseurl }}{{ page.url }}', <!-- 현재 페이지의 URL을 추적 -->
        		  'title': '{{ page.title | replace: "'", "\\\\'" }}' <!-- 현재 페이지의 제목을 추적, 제목에 따옴표가 있을 경우 이를 이스케이프 처리 -->
        		});
        	</script>
        	<!-- Google Analytics 설정 끝 -->
        {% endif %}
        {% endraw %}
        ```
        
    - Explanation
        
        이 HTML 코드 블록은 Jekyll 사이트에 Google Analytics를 설정하기 위한 것입니다. Google Analytics는 웹사이트의 방문자 트래픽을 추적하고 분석하는 도구입니다. 이 코드는 사이트의 설정 파일에 `google_analytics` 값이 있을 때만 실행됩니다.
        
    - Usage
        {% raw %}
        - **`{% if site.google_analytics %}`**: Liquid 템플릿 언어의 조건문으로, `google_analytics` 설정이 있는 경우에만 코드를 실행합니다.
        {% endraw %}
        - **`<script>`**: 자바스크립트 코드를 포함하는 HTML 요소입니다.
        - **Google Analytics**: 웹사이트 트래픽 분석 도구입니다.
        - **`ga`**: Google Analytics 추적기를 설정하고 데이터를 전송하는 함수입니다.
        - **`{{ }}`**: Liquid 템플릿 언어에서 변수를 출력하는 구문입니다.
    - Usage
        1. **조건문 설정**: 사이트의 `_config.yml` 파일에 `google_analytics` 키와 값을 설정합니다. 예를 들어:
            
            ```yaml
            google_analytics: UA-XXXXX-Y
            ```
            
        2. **스크립트 포함**: 이 코드는 사이트의 모든 페이지에 포함될 수 있도록 설정 파일이나 레이아웃 파일에 포함합니다.
        3. **트래킹 ID 사용**: `{{ site.google_analytics }}`는 설정 파일에 정의된 Google Analytics 트래킹 ID를 사용하여 추적기를 생성합니다.
        4. **페이지뷰 전송**: `ga('send', 'pageview', ...)`를 사용하여 현재 페이지의 URL과 제목을 Google Analytics에 전송합니다.
    - **Important Points**
        - **트래킹 ID**: Google Analytics 계정에서 제공된 올바른 트래킹 ID를 사용해야 합니다.
        - **조건문**: `google_analytics` 설정이 없으면 코드가 실행되지 않습니다.
        - **자바스크립트**: 자바스크립트가 비활성화된 브라우저에서는 Google Analytics가 작동하지 않을 수 있습니다.
    - **Extensions**
        - **추가 추적 설정**: 페이지뷰 외에 이벤트 추적, 사용자 정의 변수 등을 추가할 수 있습니다.
            
            ```jsx
            ga('send', 'event', 'button', 'click', 'nav-buttons');
            
            ```
            
        - **다양한 분석 도구 통합**: Google Analytics 외에도 다른 웹 분석 도구를 추가하여 더 다양한 데이터를 수집할 수 있습니다.
        - **데이터 필터링 및 세분화**: Google Analytics 대시보드에서 수집된 데이터를 필터링하고 세분화하여 더 구체적인 인사이트를 얻을 수 있습니다.
        - **추적 스크립트 최적화**: 스크립트를 비동기로 로드하여 페이지 로딩 속도를 최적화할 수 있습니다.
    
    이 HTML 코드는 Google Analytics를 설정하고 사이트 방문자 트래픽을 추적하기 위한 기본 예제입니다. 이를 통해 웹사이트의 방문자 데이터를 분석하고 개선할 수 있습니다.
    
- **disqus.html**
    - **HTML Code** with Comments
        
        ```html
        {% if site.disqus %}
        <!-- 사이트 설정에서 Disqus 설정이 있을 경우에만 실행 -->
        <div class="comments"> <!-- 댓글 섹션을 위한 div 요소 -->
        	<div id="disqus_thread"></div> <!-- Disqus 댓글을 로드할 div 요소 -->
        
        	<script type="text/javascript"> <!-- 자바스크립트 코드를 포함 -->
        	    var disqus_shortname = '{{ site.disqus }}'; <!-- Disqus의 짧은 이름 변수 설정, 사이트 설정에서 가져옴 -->
        
        	    (function() { <!-- 즉시 실행 함수로 Disqus 스크립트를 비동기로 로드 -->
        	        var dsq = document.createElement('script'); dsq.type = 'text/javascript'; dsq.async = true;
        	        dsq.src = '//' + disqus_shortname + '.disqus.com/embed.js'; <!-- Disqus 스크립트 소스 설정 -->
        	        (document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]).appendChild(dsq); <!-- Disqus 스크립트를 문서에 추가 -->
        	    })();
        
        	</script>
        
        	<noscript>Please enable JavaScript to view the <a href="<http://disqus.com/?ref_noscript>">comments powered by Disqus.</a></noscript>
        	<!-- 자바스크립트를 사용할 수 없을 때 표시될 대체 콘텐츠 -->
        </div>
        {% endif %}
        
        ```
        
    - Explanation
        
        이 HTML 코드는 Disqus 댓글 시스템을 웹 페이지에 통합하는 기능을 합니다. Disqus는 웹사이트에 댓글 기능을 추가하는 서비스입니다. 이 코드는 사이트 설정에 `disqus` 값이 있을 때만 실행됩니다.
        
    - Key Terms
        {% raw %}
        - **`{% if site.disqus %}`**: Liquid 템플릿 언어의 조건문으로, `site.disqus` 설정이 있는 경우에만 코드를 실행합니다.
        {% endraw %}
        - **`<div>`**: HTML의 블록 요소로, 다른 요소들을 그룹화합니다.
        - **`<script>`**: 자바스크립트 코드를 포함하는 HTML 요소입니다.
        - **`disqus_shortname`**: Disqus 사이트 설정에서 제공하는 고유한 사이트 식별자입니다.
        - **`document.createElement('script')`**: 새로운 스크립트 요소를 생성하는 자바스크립트 메서드입니다.
        - **`dsq.async = true`**: 스크립트를 비동기로 로드하도록 설정합니다.
        - **`<noscript>`**: 자바스크립트가 비활성화된 브라우저에서 표시될 내용을 정의하는 HTML 요소입니다.
    - Usage
        1. **Disqus 설정**: 사이트의 `_config.yml` 파일에 `disqus` 키와 값을 설정합니다. 예를 들어:
            
            ```yaml
            disqus: your-disqus-shortname
            ```
            
        2. **Disqus 스크립트 로드**: 스크립트는 페이지가 로드될 때 비동기로 로드됩니다. 이는 페이지 로드 성능을 개선하는 데 도움이 됩니다.
        3. **Disqus 댓글 표시**: `id="disqus_thread"`가 있는 `<div>` 요소에 Disqus 댓글이 삽입됩니다.
    - **Important Points**
        - **Disqus 설정 확인**: `_config.yml` 파일에 올바른 Disqus 짧은 이름을 입력해야 합니다.
        - **자바스크립트 의존성**: Disqus는 자바스크립트에 의존하므로, 자바스크립트가 비활성화된 브라우저에서는 댓글이 표시되지 않습니다.
        - **HTTPS 사용**: 가능한 경우 HTTPS를 사용하여 보안을 강화하세요.
    - **Extensions**
        - **추가 댓글 옵션 설정**: Disqus의 다양한 설정 옵션을 추가하여 댓글 기능을 커스터마이즈할 수 있습니다.
            
            ```jsx
            var disqus_config = function () {
                this.page.url = PAGE_URL;  // Replace PAGE_URL with your page's canonical URL variable
                this.page.identifier = PAGE_IDENTIFIER; // Replace PAGE_IDENTIFIER with your page's unique identifier variable
            };
            
            ```
            
        - **스타일 커스터마이징**: CSS를 사용하여 Disqus 댓글 섹션의 스타일을 커스터마이즈할 수 있습니다.
            
            ```css
            .comments {
                margin-top: 30px;
                padding: 10px;
                background-color: #f9f9f9;
            }
            
            ```
            
        - **다른 댓글 시스템 통합**: Disqus 외에도 Facebook Comments, IntenseDebate 등 다른 댓글 시스템을 통합할 수 있습니다.
        - **댓글 로딩 최적화**: 페이지 로딩 속도를 최적화하기 위해 스크롤 이벤트를 사용하여 댓글을 지연 로드할 수 있습니다.
    
    이 HTML 코드는 Disqus 댓글 시스템을 웹사이트에 통합하여 사용자가 댓글을 달고 상호작용할 수 있도록 하는 기본 예제입니다. 이를 통해 웹사이트에 댓글 기능을 쉽게 추가하고 관리할 수 있습니다.
    
- **meta.html**
    - **HTML Code** with Comments
        
        ```html
        <!-- HTML 문서의 문자 인코딩을 설정합니다. UTF-8은 유니코드 표준을 사용하는 문자 인코딩입니다. -->
        <meta charset="utf-8" />
        
        <!-- HTML 문서의 Content-Type을 설정하여 문서의 MIME 타입과 문자 인코딩을 명시합니다. -->
        <meta content='text/html; charset=utf-8' http-equiv='Content-Type'>
        
        <!-- IE 브라우저 호환성을 설정합니다. IE=edge는 최신 렌더링 엔진을 사용하게 합니다. -->
        <meta http-equiv='X-UA-Compatible' content='IE=edge'>
        
        <!-- 반응형 웹 디자인을 위해 뷰포트 메타 태그를 설정합니다. -->
        <meta name='viewport' content='width=device-width, initial-scale=1.0, maximum-scale=1.0'>
        
        <!-- 페이지에 요약이 있으면 이를 설명 메타 태그에 설정합니다. -->
        {% if page.excerpt %}
        <meta name="description" content="{{ page.excerpt| strip_html }}" />
        <meta property="og:description" content="{{ page.excerpt| strip_html }}" />
        {% else %}
        <!-- 페이지에 요약이 없으면 사이트 설명을 설명 메타 태그에 설정합니다. -->
        <meta name="description" content="{{ site.description }}">
        <meta property="og:description" content="{{ site.description }}" />
        {% endif %}
        
        <!-- 사이트 작성자를 명시하는 메타 태그입니다. -->
        <meta name="author" content="{{ site.name }}" />
        
        <!-- 페이지에 제목이 있으면 이를 Open Graph와 Twitter 카드의 제목 메타 태그에 설정합니다. -->
        {% if page.title %}
        <meta property="og:title" content="{{ page.title }}" />
        <meta property="twitter:title" content="{{ page.title }}" />
        {% endif %}
        
        ```
        
    - Explanation
        
        이 HTML 파일은 Jekyll 기반 웹사이트에서 메타 정보를 설정하는 데 사용됩니다. 메타 정보는 웹 브라우저와 검색 엔진에 페이지의 특성을 설명하고, 소셜 미디어에서 공유될 때 페이지가 어떻게 보일지 정의합니다.
        
    - Key Terms
        - **`<meta charset="utf-8" />`**: 문서의 문자 인코딩을 UTF-8로 설정합니다.
        - **`<meta content='text/html; charset=utf-8' http-equiv='Content-Type'>`**: 문서의 MIME 타입과 문자 인코딩을 설정합니다.
        - **`<meta http-equiv='X-UA-Compatible' content='IE=edge'>`**: IE 브라우저에서 최신 렌더링 엔진을 사용하게 합니다.
        - **`<meta name='viewport' content='width=device-width, initial-scale=1.0, maximum-scale=1.0'>`**: 반응형 웹 디자인을 위해 뷰포트를 설정합니다.
        - **`{% if page.excerpt %} ... {% else %} ... {% endif %}`**: Liquid 템플릿 언어의 조건문으로, `page.excerpt`가 있을 때와 없을 때 각각 다른 메타 태그를 설정합니다.
        - **`<meta name="description" content="...">`**: 페이지 설명을 설정하여 검색 엔진 최적화(SEO)를 돕습니다.
        - **`<meta property="og:description" content="...">`**: Open Graph 프로토콜을 사용하여 소셜 미디어에서 페이지 설명을 설정합니다.
        - **`<meta name="author" content="...">`**: 문서의 작성자를 설정합니다.
        - **`<meta property="og:title" content="...">`**: Open Graph 프로토콜을 사용하여 소셜 미디어에서 페이지 제목을 설정합니다.
        - **`<meta property="twitter:title" content="...">`**: Twitter 카드에서 페이지 제목을 설정합니다.
    - Usage
        1. **문자 인코딩 설정**: `<meta charset="utf-8" />`를 사용하여 페이지의 문자 인코딩을 UTF-8로 설정합니다.
        2. **브라우저 호환성 설정**: `<meta http-equiv='X-UA-Compatible' content='IE=edge'>`를 사용하여 Internet Explorer에서 최신 렌더링 엔진을 사용하게 합니다.
        3. **뷰포트 설정**: `<meta name='viewport' content='width=device-width, initial-scale=1.0, maximum-scale=1.0'>`를 사용하여 반응형 디자인을 지원합니다.
        4. **페이지 및 사이트 설명 설정**: `page.excerpt`가 있는 경우 이를 설명으로 사용하고, 없는 경우 사이트 설명을 사용합니다.
        5. **작성자 설정**: `<meta name="author" content="{{ site.name }}" />`를 사용하여 페이지 작성자를 설정합니다.
        6. **소셜 미디어 제목 설정**: `page.title`이 있는 경우 Open Graph와 Twitter 카드의 제목을 설정합니다.
    - **Important Points**
        - **문자 인코딩**: UTF-8 인코딩을 사용하여 다양한 언어와 문자를 지원합니다.
        - **브라우저 호환성**: 최신 렌더링 엔진을 사용하여 더 나은 사용자 경험을 제공합니다.
        - **반응형 디자인**: 뷰포트 설정을 통해 모바일 장치에서도 적절한 페이지 표시를 보장합니다.
        - **SEO 최적화**: 적절한 메타 태그를 사용하여 검색 엔진에서 페이지 가시성을 높입니다.
        - **소셜 미디어**: Open Graph와 Twitter 카드 설정을 통해 소셜 미디어에서 페이지가 적절하게 표시되도록 합니다.
    - **Extensions**
        - **추가 메타 태그**: SEO와 소셜 미디어 최적화를 위해 추가 메타 태그를 사용할 수 있습니다.
            
            ```html
            <meta name="keywords" content="HTML, CSS, JavaScript, Jekyll">
            <meta property="og:image" content="<https://example.com/image.jpg>">
            <meta name="twitter:card" content="summary_large_image">
            ```
            
        - **동적 메타 데이터**: Liquid 템플릿 언어를 사용하여 페이지별로 동적 메타 데이터를 설정할 수 있습니다.
            
            ```html
            <meta property="og:url" content="{{ site.url }}{{ page.url }}">
            <meta property="og:type" content="article">
            <meta property="og:site_name" content="{{ site.name }}">
            ```
            
        - **캐시 제어**: 웹 페이지 캐싱을 제어하기 위한 메타 태그를 추가할 수 있습니다.
            
            ```html
            <meta http-equiv="cache-control" content="no-cache, no-store, must-revalidate">
            <meta http-equiv="pragma" content="no-cache">
            <meta http-equiv="expires" content="0">
            ```
            
        
        이 HTML 코드는 Jekyll 기반 웹사이트에서 메타 정보를 설정하여 SEO와 소셜 미디어 최적화를 돕는 예제입니다. 메타 태그의 중요성을 이해하고 이를 확장하여 웹 페이지의 가시성과 사용자 경험을 향상시킬 수 있습니다.
        
- **svg-icons.html**
    - **HTML Code**
        
        ```html
        <!-- Dribbble 링크가 설정되어 있으면 Dribbble 아이콘을 포함하는 링크를 생성합니다 -->
        {% if site.footer-links.dribbble %}
        <a href="<https://dribbble.com/>{{ site.footer-links.dribbble }}">
            <i class="svg-icon dribbble"></i>
        </a>
        {% endif %}
        
        <!-- 이메일 주소가 설정되어 있으면 이메일 아이콘을 포함하는 메일 링크를 생성합니다 -->
        {% if site.footer-links.email %}
        <a href="mailto:{{ site.footer-links.email }}">
            <i class="svg-icon email"></i>
        </a>
        {% endif %}
        
        <!-- Facebook 링크가 설정되어 있으면 Facebook 아이콘을 포함하는 링크를 생성합니다 -->
        {% if site.footer-links.facebook %}
        <a href="<https://www.facebook.com/>{{ site.footer-links.facebook }}">
            <i class="svg-icon facebook"></i>
        </a>
        {% endif %}
        
        <!-- Flickr 링크가 설정되어 있으면 Flickr 아이콘을 포함하는 링크를 생성합니다 -->
        {% if site.footer-links.flickr %}
        <a href="<https://www.flickr.com/>{{ site.footer-links.flickr }}">
            <i class="svg-icon flickr"></i>
        </a>
        {% endif %}
        
        <!-- GitHub 링크가 설정되어 있으면 GitHub 아이콘을 포함하는 링크를 생성합니다 -->
        {% if site.footer-links.github %}
        <a href="<https://github.com/>{{ site.footer-links.github }}">
            <i class="svg-icon github"></i>
        </a>
        {% endif %}
        
        <!-- Instagram 링크가 설정되어 있으면 Instagram 아이콘을 포함하는 링크를 생성합니다 -->
        {% if site.footer-links.instagram %}
        <a href="<https://instagram.com/>{{ site.footer-links.instagram }}">
            <i class="svg-icon instagram"></i>
        </a>
        {% endif %}
        
        <!-- LinkedIn 링크가 설정되어 있으면 LinkedIn 아이콘을 포함하는 링크를 생성합니다 -->
        {% if site.footer-links.linkedin %}
        <a href="<https://www.linkedin.com/in/>{{ site.footer-links.linkedin }}">
            <i class="svg-icon linkedin"></i>
        </a>
        {% endif %}
        
        <!-- Pinterest 링크가 설정되어 있으면 Pinterest 아이콘을 포함하는 링크를 생성합니다 -->
        {% if site.footer-links.pinterest %}
        <a href="<https://www.pinterest.com/>{{ site.footer-links.pinterest }}">
            <i class="svg-icon pinterest"></i>
        </a>
        {% endif %}
        
        <!-- RSS 피드 링크가 설정되어 있으면 RSS 아이콘을 포함하는 링크를 생성합니다 -->
        {% if site.footer-links.rss %}
        <a href="{{ site.baseurl }}/feed.xml">
            <i class="svg-icon rss"></i>
        </a>
        {% endif %}
        
        <!-- Twitter 링크가 설정되어 있으면 Twitter 아이콘을 포함하는 링크를 생성합니다 -->
        {% if site.footer-links.twitter %}
        <a href="<https://www.twitter.com/>{{ site.footer-links.twitter }}">
            <i class="svg-icon twitter"></i>
        </a>
        {% endif %}
        
        <!-- Stack Overflow 링크가 설정되어 있으면 Stack Overflow 아이콘을 포함하는 링크를 생성합니다 -->
        {% if site.footer-links.stackoverflow %}
        <a href="<http://stackoverflow.com/>{{ site.footer-links.stackoverflow }}">
            <i class="svg-icon stackoverflow"></i>
        </a>
        {% endif %}
        
        <!-- YouTube 링크가 설정되어 있으면 YouTube 아이콘을 포함하는 링크를 생성합니다 -->
        {% if site.footer-links.youtube %}
        <a href="<https://youtube.com/>{{ site.footer-links.youtube }}">
            <i class="svg-icon youtube"></i>
        </a>
        {% endif %}
        
        <!-- Google Plus 링크가 설정되어 있으면 Google Plus 아이콘을 포함하는 링크를 생성합니다 -->
        {% if site.footer-links.googleplus %}
        <a href="<https://plus.google.com/>{{ site.footer-links.googleplus }}">
            <i class="svg-icon googleplus"></i>
        </a>
        {% endif %}
        
        ```
        
    - Explanation
        
        이 HTML 코드는 Jekyll 사이트의 푸터에 다양한 소셜 미디어 링크를 포함하는 아이콘을 추가하기 위해 사용됩니다. 각 소셜 미디어 링크는 사이트 설정 파일에 지정된 경우에만 표시됩니다.

    - Key Terms
        **`<a>`**: HTML의 앵커 태그로, 링크를 생성하는 요소입니다.
        **`href`**: 앵커 태그의 속성으로, 링크의 URL을 지정합니다.
        **`<i>`**: 아이콘을 나타내기 위해 사용되는 HTML 요소입니다. 보통 폰트 아이콘 라이브러리와 함께 사용됩니다.
        **`class`**: HTML 요소의 속성으로, CSS 스타일링을 위한 클래스를 지정합니다.
        **`{{ }}`**: Liquid 템플릿 언어에서 변수를 출력할 때 사용합니다.

    - Usage
        1. **사이트 설정**: `_config.yml` 파일에서 각 소셜 미디어 링크에 대한 사용자 이름 또는 이메일을 설정합니다. 예를 들어:
            
            ```yaml
            footer-links:
              dribbble: your-dribbble-username
              email: your-email@example.com
              facebook: your-facebook-username
              flickr: your-flickr-username
              github: your-github-username
              instagram: your-instagram-username
              linkedin: your-linkedin-username
              pinterest: your-pinterest-username
              rss: true
              twitter: your-twitter-username
              stackoverflow: users/your-stackoverflow-id
              youtube: your-youtube-channel
              googleplus: your-googleplus-id
            
            ```
            
        2. **링크 생성**: 설정 파일에 정의된 값에 따라 각 소셜 미디어 아이콘을 포함하는 링크를 생성합니다.
        3. **아이콘 클래스 적용**: `<i>` 태그의 클래스는 CSS나 아이콘 폰트 라이브러리(Font Awesome 등)와 함께 사용되어 아이콘을 표시합니다.
    - **Important Points**
        - **설정 확인**: 설정 파일에 올바른 사용자 이름이나 이메일을 입력해야 링크가 제대로 작동합니다.
        - **보안**: 이메일 주소를 평문으로 노출할 경우 스팸 봇에 의해 수집될 수 있으므로 주의가 필요합니다.
        - **스타일링**: 아이콘이 제대로 표시되려면 CSS와 아이콘 폰트 라이브러리가 올바르게 로드되어야 합니다.
    - **Extensions**
        - **추가 소셜 미디어 링크**: 다른 소셜 미디어 플랫폼을 추가하고 싶다면 설정 파일에 새로운 항목을 추가하고, HTML 코드에 새로운 조건문과 링크를 추가합니다.
            
            ```html
            {% if site.footer-links.tiktok %}
            <a href="<https://www.tiktok.com/@>{{ site.footer-links.tiktok }}">
                <i class="svg-icon tiktok"></i>
            </a>
            {% endif %}
            ```
            
        - **아이콘 스타일링**: CSS를 사용하여 아이콘의 크기, 색상 등을 커스터마이징할 수 있습니다.
            
            ```css
            .svg-icon {
                width: 24px;
                height: 24px;
                fill: #000; /* 기본 색상 설정 */
            }
            .svg-icon:hover {
                fill: #ff4500; /* 마우스를 올렸을 때 색상 변경 */
            }
            ```
            
        - **스크립트 추가**: 각 소셜 미디어 아이콘에 추가 기능을 제공하기 위해 자바스크립트를 추가할 수 있습니다. 예를 들어, 클릭 이벤트를 추적할 수 있습니다.
            
            ```jsx
            document.querySelectorAll('.svg-icon').forEach(icon => {
                icon.addEventListener('click', function() {
                    console.log('Icon clicked: ' + this.classList);
                });
            });
            ```
            
        
        이 HTML 코드는 Jekyll 기반 웹사이트의 푸터에 소셜 미디어 링크를 추가하는 기본 예제입니다. 이를 통해 웹사이트 방문자들이 다양한 소셜 미디어 플랫폼에서 쉽게 소통할 수 있도록 합니다.
        

## 3) css 파일

- **style.scss**
    
    ### CSS Code with Comments
    
    ```css
    //
    // IMPORTS
    //
    
    @import "reset"; /* CSS 초기화를 위해 reset 스타일을 가져옵니다. */
    @import "variables"; /* CSS에서 사용할 변수들을 가져옵니다. */
    
     /**************/
     /* BASE RULES */
     /**************/
    
    html {
      font-size: 100%; /* 기본 글꼴 크기를 설정합니다. 브라우저 기본값은 16px입니다. */
    }
    
    body {
      background: $white; /* body의 배경색을 흰색으로 설정합니다. 변수 $white를 사용합니다. */
      font: 18px/1.4 $helvetica; /* 글꼴을 Helvetica로 설정하고 크기는 18px, 줄 높이는 1.4로 설정합니다. */
      color: $darkGray; /* 텍스트 색상을 어두운 회색으로 설정합니다. 변수 $darkGray를 사용합니다. */
    }
    
    .container {
      margin: 0 auto; /* 컨테이너를 수평 중앙에 배치합니다. */
      max-width: 740px; /* 최대 너비를 740px로 제한합니다. */
      padding: 0 10px; /* 컨테이너 내부의 좌우 여백을 10px로 설정합니다. */
      width: 100%; /* 너비를 100%로 설정하여 부모 요소의 너비를 채웁니다. */
    }
    
    h1, h2, h3, h4, h5, h6 {
      font-family: $helveticaNeue; /* 제목 요소의 글꼴을 Helvetica Neue로 설정합니다. */
      color: $darkerGray; /* 텍스트 색상을 더 어두운 회색으로 설정합니다. 변수 $darkerGray를 사용합니다. */
      font-weight: bold; /* 텍스트를 굵게 설정합니다. */
    
      line-height: 1.7; /* 줄 높이를 1.7로 설정합니다. */
      margin: 1em 0 15px; /* 위쪽 여백을 1em, 아래쪽 여백을 15px로 설정합니다. */
      padding: 0; /* 내부 여백을 0으로 설정합니다. */
    
      @include mobile { /* 모바일 디바이스용 미디어 쿼리입니다. */
        line-height: 1.4; /* 모바일에서는 줄 높이를 1.4로 설정합니다. */
      }
    }
    
    h1 {
      font-size: 30px; /* h1 요소의 글꼴 크기를 30px로 설정합니다. */
      a {
        color: inherit; /* a 요소의 색상을 부모 요소의 색상과 동일하게 설정합니다. */
      }
    }
    
    h2 {
      font-size: 24px; /* h2 요소의 글꼴 크기를 24px로 설정합니다. */
    }
    
    h3 {
      font-size: 20px; /* h3 요소의 글꼴 크기를 20px로 설정합니다. */
    }
    
    h4 {
      font-size: 18px; /* h4 요소의 글꼴 크기를 18px로 설정합니다. */
      color: $gray; /* 텍스트 색상을 회색으로 설정합니다. 변수 $gray를 사용합니다. */
    }
    
    p {
      margin: 15px 0; /* p 요소의 위쪽과 아래쪽 여백을 15px로 설정합니다. */
    }
    
    a {
      color: $blue; /* 링크 색상을 파란색으로 설정합니다. 변수 $blue를 사용합니다. */
      text-decoration: none; /* 링크의 밑줄을 제거합니다. */
      cursor: pointer; /* 링크에 마우스 커서를 올리면 포인터 커서로 변경합니다. */
      &:hover, &:active { /* 링크가 호버되거나 활성화될 때 스타일을 설정합니다. */
        color: $blue; /* 색상을 파란색으로 설정합니다. */
      }
    }
    
    ul, ol {
      margin: 15px 0; /* 리스트의 위쪽과 아래쪽 여백을 15px로 설정합니다. */
      padding-left: 30px; /* 리스트 아이템의 왼쪽 여백을 30px로 설정합니다. */
    }
    
    ul {
      list-style-type: disc; /* ul 리스트 아이템의 기본 불릿 스타일을 디스크로 설정합니다. */
    }
    
    ol {
      list-style-type: decimal; /* ol 리스트 아이템의 기본 번호 스타일을 십진수로 설정합니다. */
    }
    
    ol ul, ul ol, ul ul, ol ol {
      margin: 0; /* 중첩된 리스트의 여백을 0으로 설정합니다. */
    }
    
    ul ul, ol ul {
      list-style-type: circle; /* 중첩된 ul 리스트 아이템의 불릿 스타일을 원으로 설정합니다. */
    }
    
    em, i {
      font-style: italic; /* em 및 i 요소를 이탤릭체로 설정합니다. */
    }
    
    strong, b {
      font-weight: bold; /* strong 및 b 요소를 굵게 설정합니다. */
    }
    
    img {
      max-width: 100%; /* 이미지의 최대 너비를 100%로 설정하여 부모 요소의 너비를 넘지 않도록 합니다. */
    }
    
    // Google Translate 팝업 상자 내 이미지의 최대 너비를 원래대로 설정합니다.
    .gmnoprint img {
      max-width: none;
    }
    
    .date {
      font-style: italic; /* 날짜 텍스트를 이탤릭체로 설정합니다. */
      color: $gray; /* 텍스트 색상을 회색으로 설정합니다. */
    }
    
    // 선택된 텍스트의 색상과 배경을 설정합니다.
    ::-moz-selection {
      color: $black; /* 선택된 텍스트의 색상을 검은색으로 설정합니다. */
      background: $lightGray; /* 선택된 텍스트의 배경색을 밝은 회색으로 설정합니다. */
    }
    ::selection {
      color: $black; /* 선택된 텍스트의 색상을 검은색으로 설정합니다. */
      background: $lightGray; /* 선택된 텍스트의 배경색을 밝은 회색으로 설정합니다. */
    }
    
    // Nicolas Gallagher의 clearfix 해킹을 적용합니다.
    // <http://nicolasgallagher.com/micro-clearfix-hack/>
    .clearfix:before,
    .clearfix:after {
        content: " ";
        display: table;
    }
    
    .clearfix:after {
        clear: both;
    }
    
    /*********************/
    /* LAYOUT / SECTIONS */
    /*********************/
    
    //
    // .masthead
    //
    
    .wrapper-masthead {
      margin-bottom: 50px; /* masthead의 아래쪽 여백을 50px로 설정합니다. */
    }
    
    .masthead {
      padding: 20px 0; /* masthead의 상하 패딩을 20px로 설정합니다. */
      border-bottom: 1px solid $lightGray; /* 아래쪽 경계선을 밝은 회색 실선으로 설정합니다. */
    
      @include mobile { /* 모바일 디바이스용 미디어 쿼리입니다. */
        text-align: center; /* 텍스트를 가운데 정렬합니다. */
      }
    }
    
    .site-avatar {
      float: left; /* 사이트 아바타를 왼쪽으로 정렬합니다. */
      width: 70px; /* 너비를 70px로 설정합니다. */
      height: 70px; /* 높이를 70px로 설정합니다. */
      margin-right: 15px; /* 오른쪽 여백을 15px로 설정합니다. */
    
      @include mobile { /* 모바일 디바이스용 미디어 쿼리입니다. */
        float: none; /* 정렬을 해제합니다. */
        display: block; /* 블록 요소로 설정합니다. */
        margin: 0 auto; /* 아바타를 가운데 정렬합니다. */
      }
    
      img {
        border-radius: 5px; /* 이미지의 모서리를 5px 반경으로 둥글게 설정합니다. */
      }
    }
    
    .site-info {
      float: left; /* 사이트 정보를 왼쪽으로 정렬합니다. */
    
      @include mobile { /* 모바일 디바이스용 미디어 쿼리입니다. */
        float: none; /* 정렬을 해제합니다. */
        display: block; /* 블록 요소로 설정합니다. */
        margin: 0 auto; /* 사이트 정보를 가운데 정렬합니다. */
      }
    }
    
    .site-name {
      margin: 0; /* 여백을 0으로 설정합니다. */
      color: $darkGray; /* 텍스트 색상을 어두운 회색으로 설정합니다. */
      cursor: pointer; /* 마우스 커서를 포인터로 설정합니다. */
      font-family: $helveticaNeue; /* 글꼴을 Helvetica Neue로 설정합니다. */
      font-weight: 300; /* 글꼴 두께를 300으로 설정합니다. */
      font-size: 28px; /* 글꼴 크기를 28px로 설정합니다. */
      letter-spacing: 1px; /* 글자 간격을 1px로 설정합니다. */
    }
    
    .site-description {
      margin: -5px 0 0 0; /* 위쪽 여백을 -5px로 설정하여 텍스트를 더 가까이 배치합니다. */
      color: $gray; /* 텍스트 색상을 회색으로 설정합니다. */
      font-size: 16px; /* 글꼴 크기를 16px로 설정합니다. */
    
      @include mobile { /* 모바일 디바이스용 미디어 쿼리입니다. */
        margin: 3px 0; /* 여백을
    
     3px로 설정합니다. */
      }
    }
    
    nav {
      float: right; /* 내비게이션을 오른쪽으로 정렬합니다. */
      margin-top: 23px; /* 상단 여백을 23px로 설정하여 수직 가운데 정렬을 시도합니다. */
      font-family: $helveticaNeue; /* 글꼴을 Helvetica Neue로 설정합니다. */
      font-size: 18px; /* 글꼴 크기를 18px로 설정합니다. */
    
      @include mobile { /* 모바일 디바이스용 미디어 쿼리입니다. */
        float: none; /* 정렬을 해제합니다. */
        margin-top: 9px; /* 상단 여백을 9px로 설정합니다. */
        display: block; /* 블록 요소로 설정합니다. */
        font-size: 16px; /* 글꼴 크기를 16px로 설정합니다. */
      }
    
      a {
        margin-left: 20px; /* 왼쪽 여백을 20px로 설정합니다. */
        color: $darkGray; /* 텍스트 색상을 어두운 회색으로 설정합니다. */
        text-align: right; /* 텍스트를 오른쪽 정렬합니다. */
        font-weight: 300; /* 글꼴 두께를 300으로 설정합니다. */
        letter-spacing: 1px; /* 글자 간격을 1px로 설정합니다. */
    
        @include mobile { /* 모바일 디바이스용 미디어 쿼리입니다. */
          margin: 0 10px; /* 좌우 여백을 10px로 설정합니다. */
          color: $blue; /* 텍스트 색상을 파란색으로 설정합니다. */
        }
      }
    }
    
    //
    // .main
    //
    
    .posts > .post {
      padding-bottom: 2em; /* 각 포스트의 하단 패딩을 2em으로 설정합니다. */
      border-bottom: 1px solid $lightGray; /* 하단 경계선을 밝은 회색 실선으로 설정합니다. */
    }
    
    .posts > .post:last-child {
      padding-bottom: 1em; /* 마지막 포스트의 하단 패딩을 1em으로 설정합니다. */
      border-bottom: none; /* 마지막 포스트는 하단 경계선을 제거합니다. */
    }
    
    .post {
      blockquote {
        margin: 1.8em .8em; /* 상하 여백을 1.8em, 좌우 여백을 0.8em으로 설정합니다. */
        border-left: 2px solid $gray; /* 왼쪽 경계선을 회색 실선으로 설정합니다. */
        padding: 0.1em 1em; /* 상하 패딩을 0.1em, 좌우 패딩을 1em으로 설정합니다. */
        color: $gray; /* 텍스트 색상을 회색으로 설정합니다. */
        font-size: 22px; /* 글꼴 크기를 22px로 설정합니다. */
        font-style: italic; /* 이탤릭체로 설정합니다. */
      }
    
      .comments {
        margin-top: 10px; /* 상단 여백을 10px로 설정합니다. */
      }
    
      .read-more {
        text-transform: uppercase; /* 텍스트를 대문자로 변환합니다. */
        font-size: 15px; /* 글꼴 크기를 15px로 설정합니다. */
      }
    }
    
    .wrapper-footer {
      margin-top: 50px; /* 상단 여백을 50px로 설정합니다. */
      border-top: 1px solid #ddd; /* 상단 경계선을 밝은 회색 실선으로 설정합니다. */
      border-bottom: 1px solid #ddd; /* 하단 경계선을 밝은 회색 실선으로 설정합니다. */
      background-color: $lightGray; /* 배경색을 밝은 회색으로 설정합니다. */
    }
    
    footer {
      padding: 20px 0; /* 상하 패딩을 20px로 설정합니다. */
      text-align: center; /* 텍스트를 가운데 정렬합니다. */
    }
    
    // 코드의 상단에 위치한 syntax highlighting 임포트를 코드 하단으로 이동
    @import "highlights"; /* 하이라이트 스타일을 가져옵니다. */
    @import "svg-icons"; /* SVG 아이콘 스타일을 가져옵니다. */
    
    ```
    
    ### Explanation
    
    이 CSS 코드는 HTML 페이지의 다양한 요소를 스타일링합니다. 아래는 각 섹션의 의도와 설명입니다:
    
    - **Imports**: CSS 파일에서 다른 스타일 시트를 가져옵니다. `reset`은 모든 브라우저에서 일관된 스타일링을 보장하기 위해 기본 스타일을 초기화합니다. `variables`는 재사용 가능한 변수들을 정의합니다.
    - **Base Rules**: HTML 및 body 요소의 기본 스타일을 정의합니다. 글꼴 크기, 배경색, 글꼴 패밀리 등을 설정합니다.
    - **Container**: 중앙 정렬된 반응형 레이아웃을 위해 사용됩니다.
    - **Headings**: 제목 요소(h1~h6)의 글꼴, 색상, 여백, 줄 높이 등을 정의합니다. 모바일 장치에서는 줄 높이를 다르게 설정합니다.
    - **Paragraphs & Links**: 문단과 링크의 기본 스타일을 설정합니다. 문단의 여백, 링크의 색상 및 호버 스타일을 정의합니다.
    - **Lists**: 순서 있는 리스트(ol)와 순서 없는 리스트(ul)의 스타일을 설정합니다.
    - **Text Styles**: 이탤릭체(em, i)와 굵은 텍스트(strong, b)를 설정합니다.
    - **Images**: 이미지가 부모 요소의 너비를 넘지 않도록 설정합니다.
    - **Date**: 날짜 텍스트를 이탤릭체와 회색으로 설정합니다.
    - **Selection**: 선택된 텍스트의 배경과 색상을 설정합니다.
    - **Clearfix**: 레이아웃 정리를 위한 clearfix 해킹을 적용합니다.
    - **Masthead**: 사이트 헤더의 레이아웃과 스타일을 설정합니다.
    - **Main**: 본문 영역의 스타일을 설정합니다. 게시물과 댓글, 인용구 등의 스타일을 정의합니다.
    - **Footer**: 사이트 하단의 스타일을 설정합니다.
    
    ### Key Terms
    
    - `@import`: 다른 CSS 파일을 가져와서 사용할 수 있습니다.
    - `font-family`: 글꼴을 지정합니다.
    - `background`: 배경 속성을 설정합니다.
    - `font`: 글꼴 스타일, 크기, 줄 높이를 한 번에 설정합니다.
    - `margin`, `padding`: 요소의 외부 및 내부 여백을 설정합니다.
    - `color`: 텍스트 색상을 지정합니다.
    - `text-align`: 텍스트 정렬을 설정합니다.
    - `font-size`: 글꼴 크기를 지정합니다.
    - `line-height`: 줄 높이를 설정합니다.
    - `@include`: Sass 믹스인을 포함합니다. 여기서는 미디어 쿼리용으로 사용됩니다.
    
    ### Usage
    
    - CSS를 사용하여 웹 페이지의 스타일을 일관되게 적용할 수 있습니다.
    - 변수($variable)와 믹스인(@include)을 사용하여 코드 재사용성과 유지 보수성을 높일 수 있습니다.
    - 미디어 쿼리를 사용하여 반응형 디자인을 구현할 수 있습니다.
    
    ### Important Points
    
    - CSS 변수와 믹스인을 사용하여 코드의 가독성과 재사용성을 높이세요.
    - 항상 유효한 CSS를 작성하고, 브라우저 호환성을 고려하세요.
    - Clearfix 해킹을 사용하여 부유 요소가 레이아웃을 깨지 않도록 하세요.
    
    ### Extensions
    
    - **미디어 쿼리**: 다양한 장치와 화면 크기에 맞춰 스타일을 조정할 수 있습니다.
    - **Flexbox와 Grid**: 더 복잡한 레이아웃을 만들 수 있습니다.
    - **애니메이션**: CSS 애니메이션과 전환을 추가하여 사용자 경험을 향상시킬 수 있습니다.

### _sass 디렉토리

- **CSS Code : _highlights.scss**
    - **CSS Code with Comments**
        
        ```css
        .highlight {
          background-color: #efefef; /* 요소의 배경색을 연한 회색(#efefef)으로 설정합니다. */
          padding: 7px 7px 7px 10px; /* 요소의 상하좌우 패딩을 설정합니다. 좌우는 7px, 왼쪽은 10px입니다. */
          border: 1px solid #ddd; /* 요소의 테두리를 연한 회색(#ddd) 실선으로 설정합니다. */
          -moz-box-shadow: 3px 3px rgba(0,0,0,0.1); /* Mozilla 브라우저용 그림자 효과를 설정합니다. */
          -webkit-box-shadow: 3px 3px rgba(0,0,0,0.1); /* Webkit 기반 브라우저용 그림자 효과를 설정합니다. */
          box-shadow: 3px 3px rgba(0,0,0,0.1); /* 요소의 그림자 효과를 설정합니다. */
          margin: 20px 0 20px 0; /* 요소의 상하 여백을 20px로 설정합니다. */
          overflow: scroll; /* 요소 내용이 넘칠 경우 스크롤바를 표시합니다. */
        }
        
        code {
          font-family:'Bitstream Vera Sans Mono','Courier', monospace; /* 코드 요소의 글꼴을 고정폭 글꼴로 설정합니다. */
        }
        
        .highlight .c { color: #586E75 } /* 주석 텍스트 색상을 설정합니다. */
        .highlight .err { color: #93A1A1 } /* 에러 텍스트 색상을 설정합니다. */
        .highlight .g { color: #93A1A1 } /* 일반 텍스트 색상을 설정합니다. */
        .highlight .k { color: #859900 } /* 키워드 텍스트 색상을 설정합니다. */
        .highlight .l { color: #93A1A1 } /* 리터럴 텍스트 색상을 설정합니다. */
        .highlight .n { color: #93A1A1 } /* 이름 텍스트 색상을 설정합니다. */
        .highlight .o { color: #859900 } /* 연산자 텍스트 색상을 설정합니다. */
        .highlight .x { color: #CB4B16 } /* 기타 텍스트 색상을 설정합니다. */
        .highlight .p { color: #93A1A1 } /* 구두점 텍스트 색상을 설정합니다. */
        .highlight .cm { color: #586E75 } /* 멀티라인 주석 텍스트 색상을 설정합니다. */
        .highlight .cp { color: #859900 } /* 전처리기 주석 텍스트 색상을 설정합니다. */
        .highlight .c1 { color: #586E75 } /* 싱글라인 주석 텍스트 색상을 설정합니다. */
        .highlight .cs { color: #859900 } /* 특별 주석 텍스트 색상을 설정합니다. */
        .highlight .gd { color: #2AA198 } /* 삭제된 텍스트 색상을 설정합니다. */
        .highlight .ge { color: #93A1A1; font-style: italic } /* 이탤릭체 강조 텍스트 색상을 설정합니다. */
        .highlight .gr { color: #DC322F } /* 에러 텍스트 색상을 설정합니다. */
        .highlight .gh { color: #CB4B16 } /* 제목 텍스트 색상을 설정합니다. */
        .highlight .gi { color: #859900 } /* 삽입된 텍스트 색상을 설정합니다. */
        .highlight .go { color: #93A1A1 } /* 출력 텍스트 색상을 설정합니다. */
        .highlight .gp { color: #93A1A1 } /* 프롬프트 텍스트 색상을 설정합니다. */
        .highlight .gs { color: #93A1A1; font-weight: bold } /* 굵은 강조 텍스트 색상을 설정합니다. */
        .highlight .gu { color: #CB4B16 } /* 서브 제목 텍스트 색상을 설정합니다. */
        .highlight .gt { color: #93A1A1 } /* 트레이스백 텍스트 색상을 설정합니다. */
        .highlight .kc { color: #CB4B16 } /* 상수 키워드 텍스트 색상을 설정합니다. */
        .highlight .kd { color: #268BD2 } /* 선언 키워드 텍스트 색상을 설정합니다. */
        .highlight .kn { color: #859900 } /* 네임스페이스 키워드 텍스트 색상을 설정합니다. */
        .highlight .kp { color: #859900 } /* 의사 키워드 텍스트 색상을 설정합니다. */
        .highlight .kr { color: #268BD2 } /* 예약어 키워드 텍스트 색상을 설정합니다. */
        .highlight .kt { color: #DC322F } /* 타입 키워드 텍스트 색상을 설정합니다. */
        .highlight .ld { color: #93A1A1 } /* 날짜 리터럴 텍스트 색상을 설정합니다. */
        .highlight .m { color: #2AA198 } /* 숫자 리터럴 텍스트 색상을 설정합니다. */
        .highlight .s { color: #2AA198 } /* 문자열 리터럴 텍스트 색상을 설정합니다. */
        .highlight .na { color: #93A1A1 } /* 속성 이름 텍스트 색상을 설정합니다. */
        .highlight .nb { color: #B58900 } /* 내장 텍스트 색상을 설정합니다. */
        .highlight .nc { color: #268BD2 } /* 클래스 이름 텍스트 색상을 설정합니다. */
        .highlight .no { color: #CB4B16 } /* 상수 이름 텍스트 색상을 설정합니다. */
        .highlight .nd { color: #268BD2 } /* 데코레이터 이름 텍스트 색상을 설정합니다. */
        .highlight .ni { color: #CB4B16 } /* 엔티티 이름 텍스트 색상을 설정합니다. */
        .highlight .ne { color: #CB4B16 } /* 예외 이름 텍스트 색상을 설정합니다. */
        .highlight .nf { color: #268BD2 } /* 함수 이름 텍스트 색상을 설정합니다. */
        .highlight .nl { color: #93A1A1 } /* 라벨 이름 텍스트 색상을 설정합니다. */
        .highlight .nn { color: #93A1A1 } /* 네임스페이스 이름 텍스트 색상을 설정합니다. */
        .highlight .nx { color: #555 } /* 기타 이름 텍스트 색상을 설정합니다. */
        .highlight .py { color: #93A1A1 } /* 속성 이름 텍스트 색상을 설정합니다. */
        .highlight .nt { color: #268BD2 } /* 태그 이름 텍스트 색상을 설정합니다. */
        .highlight .nv { color: #268BD2 } /* 변수 이름 텍스트 색상을 설정합니다. */
        .highlight .ow { color: #859900 } /* 연산자 단어 텍스트 색상을 설정합니다. */
        .highlight .w { color: #93A1A1 } /* 공백 텍스트 색상을 설정합니다. */
        .highlight .mf { color: #2AA198 } /* 부동 소수점 숫자 리터럴 텍스트 색상을 설정합니다. */
        .highlight .mh { color: #2AA198 } /* 16진수 숫자 리터럴 텍스트 색상을 설정합니다. */
        .highlight .mi { color: #2AA198 } /* 정수 숫자 리터럴 텍스트 색상을 설정합니다. */
        .highlight .mo { color: #2AA198 } /* 8진수 숫자 리터럴 텍스트 색상을 설정합니다. */
        .highlight .sb { color: #586E75 } /* 백틱 문자열 리터럴 텍스트 색상을 설정합니다. */
        .highlight .sc { color: #2AA198 } /* 문자 리터럴 텍스트 색상을 설정합니다. */
        .highlight .sd { color: #93A1A1 } /* 문서 문자열 리터럴 텍스트 색상을 설정합니다. */
        .highlight .s2 { color: #2AA198 } /* 이중 따옴표 문자열 리터럴 텍스트 색상을 설정합니다. */
        .highlight .se { color: #CB4B16 } /* 이스케이프 문자열 리터럴 텍스트 색상을 설정합니다. */
        .highlight .sh { color: #93A1A1 } /* 헤레독 문자열 리터럴 텍스트 색상을 설정합니다. */
        .highlight .si { color: #2AA198 } /* 인터폴 문자열 리터럴 텍스트 색상을 설정합니다. */
        .highlight .sx { color: #2AA198 } /* 기타 문자열 리터럴 텍스트 색상을 설정합니다. */
        .highlight .sr { color: #DC322F } /* 정규 표현식 문자열 리터럴 텍스트 색상을 설정합니다. */
        .highlight .s1 { color: #2AA198 } /* 단일 따옴표 문자열 리터럴 텍스트 색상을 설정합니다. */
        .highlight .ss { color: #2AA198 } /* 심볼 문자열 리터럴 텍스트 색상을 설정합니다. */
        .highlight .bp { color: #268BD2 } /* 내장 의사 텍스트 색상을 설정합니다. */
        .highlight .vc { color: #268BD2 } /* 클래스 변수 이름 텍스트 색상을 설정합니다. */
        .highlight .vg { color: #268BD2 } /* 전역 변수 이름 텍스트 색상을 설정합니다. */
        .highlight .vi { color: #268BD
        
        2 } /* 인스턴스 변수 이름 텍스트 색상을 설정합니다. */
        .highlight .il { color: #2AA198 } /* 긴 정수 숫자 리터럴 텍스트 색상을 설정합니다. */
        
        ```
        
    - **Explanation**
        
        이 CSS 코드는 코드 하이라이팅을 위한 스타일을 정의합니다. 특히, 코드 블록과 코드 내 특정 요소들의 스타일을 설정하여 가독성을 높입니다.
        
        - `.highlight` 클래스는 코드 블록의 스타일을 정의합니다.
            - `background-color`: 코드 블록의 배경색을 설정합니다.
            - `padding`: 코드 블록 내부의 여백을 설정합니다.
            - `border`: 코드 블록의 테두리를 설정합니다.
            - `box-shadow`: 코드 블록에 그림자 효과를 추가하여 입체감을 줍니다.
            - `margin`: 코드 블록의 외부 여백을 설정합니다.
            - `overflow: scroll`: 코드 블록이 넘칠 경우 스크롤바를 표시합니다.
        - `code` 요소는 코드 글꼴을 설정합니다.
        - `.highlight .[class]` 스타일은 코드 내 특정 요소들의 색상을 정의합니다.
            - 예: `.highlight .c`는 주석 텍스트의 색상을 설정합니다.
            - `.highlight .k`는 키워드 텍스트의 색상을 설정합니다.
    - **Key Terms**
        - `background-color`: 요소의 배경 색상을 설정합니다.
        - `padding`: 요소 내부의 여백을 설정합니다.
        - `border`: 요소의 테두리를 설정합니다.
        - `box-shadow`: 요소의 그림자 효과를 설정합니다.
        - `margin`: 요소 외부의 여백을 설정합니다.
        - `overflow`: 요소의 넘침 속성을 설정합니다.
        - `font-family`: 텍스트의 글꼴을 설정합니다.
        - `color`: 텍스트의 색상을 설정합니다.
    - **Usage**
        - 코드 블록에 배경색과 패딩을 설정하여 가독성을 높일 수 있습니다.
        - 코드 내 특정 요소들의 색상을 설정하여 구분이 쉽게 할 수 있습니다.
        - `box-shadow` 속성을 사용하여 코드 블록에 입체감을 줄 수 있습니다.
    - **Important Points**
        - `background-color`와 `color`를 조화롭게 사용하여 가독성을 높이세요.
        - `padding`과 `margin`을 적절히 설정하여 코드 블록이 다른 요소와 겹치지 않도록 하세요.
        - `overflow` 속성을 사용하여 코드 블록이 넘칠 경우 스크롤바를 표시하여 내용을 모두 볼 수 있게 하세요.
    - **Extensions**
        - **미디어 쿼리**: 다양한 화면 크기에서 코드 블록의 스타일을 조정할 수 있습니다.
        - **CSS 변수**: 색상, 패딩, 마진 등의 값을 변수로 정의하여 유지 보수성을 높일 수 있습니다.
        - **애니메이션**: 코드 블록에 애니메이션을 추가하여 사용자 경험을 향상시킬 수 있습니다.
- **_reset.scss**
    - **CSS Code with Comments**
        
        ```css
        /***************/
        /* MEYER RESET */
        /***************/
        
        /* 모든 요소들의 기본 스타일을 초기화합니다.
           브라우저마다 기본 스타일이 다르기 때문에 일관성을 유지하기 위해 사용합니다. */
        
        html, body, div, span, applet, object, iframe,
        h1, h2, h3, h4, h5, h6, p, blockquote, pre,
        a, abbr, acronym, address, big, cite, code,
        del, dfn, em, img, ins, kbd, q, s, samp,
        small, strike, strong, sub, sup, tt, var,
        b, u, i, center,
        dl, dt, dd, ol, ul, li,
        fieldset, form, label, legend,
        table, caption, tbody, tfoot, thead, tr, th, td,
        article, aside, canvas, details, embed,
        figure, figcaption, footer, header, hgroup,
        menu, nav, output, ruby, section, summary,
        time, mark, audio, video {
        	margin: 0; /* 모든 요소의 기본 여백을 제거합니다. */
        	padding: 0; /* 모든 요소의 기본 패딩을 제거합니다. */
        	border: 0; /* 모든 요소의 기본 테두리를 제거합니다. */
        	font-size: 100%; /* 폰트 크기를 초기화하여 상속받은 크기를 유지합니다. */
        	font: inherit; /* 폰트를 초기화하여 상속받은 폰트를 유지합니다. */
        	vertical-align: baseline; /* 요소들의 수직 정렬을 초기화합니다. */
        }
        
        /* HTML5의 새로운 요소들을 블록 요소로 설정합니다.
           이는 오래된 브라우저에서 이 요소들이 올바르게 렌더링되도록 하기 위함입니다. */
        article, aside, details, figcaption, figure,
        footer, header, hgroup, menu, nav, section {
        	display: block; /* 블록 요소로 설정합니다. */
        }
        
        body {
        	line-height: 1; /* 기본 줄 높이를 1로 설정하여 텍스트 간격을 초기화합니다. */
        }
        
        ol, ul {
        	list-style: none; /* 리스트 아이템의 기본 불릿 스타일을 제거합니다. */
        }
        
        blockquote, q {
        	quotes: none; /* 인용구의 기본 인용 부호 스타일을 제거합니다. */
        }
        
        blockquote:before, blockquote:after,
        q:before, q:after {
        	content: ''; /* 인용구 요소의 가상 요소 내용을 제거합니다. */
        	content: none; /* 인용구 요소의 가상 요소 내용을 제거합니다. */
        }
        
        table {
        	border-collapse: collapse; /* 테이블 셀 간의 간격을 제거합니다. */
        	border-spacing: 0; /* 테이블 셀 간의 간격을 0으로 설정합니다. */
        }
        
        /* 모든 요소에 자연스러운 박스 레이아웃 모델을 적용합니다.
           이는 요소의 크기를 계산할 때 padding과 border를 포함시킵니다. */
        *, *:before, *:after {
          -moz-box-sizing: border-box; /* Firefox 브라우저용 박스 모델 설정 */
          -webkit-box-sizing: border-box; /* Webkit 기반 브라우저용 박스 모델 설정 */
          box-sizing: border-box; /* 박스 모델을 border-box로 설정하여 padding과 border를 포함시킵니다. */
        }
        
        ```
        
    - **Explanation**
        
        이 CSS 코드는 기본적인 스타일을 초기화하고 일관성을 유지하기 위한 "Meyer Reset"을 구현합니다. 이를 통해 브라우저 간의 스타일 차이를 최소화하고, 모든 요소가 동일한 초기 상태에서 시작할 수 있도록 합니다.
        
        - **Reset Styles**:
            - `margin`, `padding`, `border`를 0으로 설정하여 기본 여백, 패딩, 테두리를 제거합니다.
            - `font-size`와 `font`를 초기화하여 폰트 크기와 폰트를 상속된 값으로 설정합니다.
            - `vertical-align: baseline`으로 요소들의 수직 정렬을 초기화합니다.
        - **HTML5 Elements**:
            - HTML5의 새로운 요소들을 블록 요소로 설정하여 오래된 브라우저에서도 올바르게 표시되도록 합니다.
        - **Body**:
            - 기본 줄 높이를 1로 설정하여 텍스트 간격을 초기화합니다.
        - **Lists**:
            - 리스트 아이템의 기본 불릿 스타일을 제거하여 리스트가 깔끔하게 보이도록 합니다.
        - **Blockquotes and Quotes**:
            - 인용구의 기본 인용 부호 스타일을 제거하여 불필요한 내용이 표시되지 않도록 합니다.
        - **Tables**:
            - 테이블 셀 간의 간격을 제거하여 테이블이 일관되게 보이도록 합니다.
        - **Box-Sizing**:
            - 모든 요소에 자연스러운 박스 레이아웃 모델을 적용하여 요소의 크기를 계산할 때 padding과 border를 포함시킵니다.
    - **Key Terms**
        - `margin`: 요소 주위의 공간을 설정합니다.
        - `padding`: 요소 내부의 콘텐츠와 경계 사이의 공간을 설정합니다.
        - `border`: 요소의 테두리를 설정합니다.
        - `font-size`: 텍스트의 크기를 설정합니다.
        - `font`: 텍스트의 글꼴 스타일을 설정합니다.
        - `vertical-align`: 요소의 수직 정렬을 설정합니다.
        - `display`: 요소의 디스플레이 유형을 설정합니다.
        - `line-height`: 텍스트의 줄 높이를 설정합니다.
        - `list-style`: 리스트 아이템의 스타일을 설정합니다.
        - `quotes`: 인용구의 스타일을 설정합니다.
        - `content`: 가상 요소의 내용을 설정합니다.
        - `border-collapse`: 테이블 셀 간의 간격을 설정합니다.
        - `box-sizing`: 요소의 크기를 계산할 때 포함되는 부분을 설정합니다.
    - **Usage**
        - Reset 스타일을 사용하여 모든 브라우저에서 일관된 스타일을 유지할 수 있습니다.
        - HTML5 요소를 블록 요소로 설정하여 오래된 브라우저에서도 올바르게 표시되도록 할 수 있습니다.
        - `box-sizing: border-box`를 사용하여 요소의 크기를 계산할 때 padding과 border를 포함시켜 레이아웃을 쉽게 관리할 수 있습니다.
    - **Important Points**
        - Reset 스타일을 사용할 때는 모든 기본 스타일이 제거되므로, 필요한 경우 각 요소에 다시 스타일을 적용해야 합니다.
        - `box-sizing: border-box`를 사용하면 요소의 크기를 계산할 때 padding과 border를 포함시키므로, 레이아웃을 쉽게 관리할 수 있습니다.
        - HTML5 요소를 블록 요소로 설정하여 오래된 브라우저에서의 호환성을 유지할 수 있습니다.
    - **Extensions**
        - **미디어 쿼리**: 다양한 화면 크기에서 스타일을 조정할 수 있습니다.
        - **CSS 변수**: 색상, 패딩, 마진 등의 값을 변수로 정의하여 유지 보수성을 높일 수 있습니다.
        - **애니메이션**: 요소에 애니메이션을 추가하여 사용자 경험을 향상시킬 수 있습니다.
- **_svg-icons.scss**
    - **CSS Code :  _sass/_svg-icons.scss**
        
        Jekyll에서 Sass 파일 작성 및 적용 방법으로 설명을 대신합니다: - 이유는 **파일 읽기 에러**
        
    
    ### **Jekyll Now애서 _sass/_svg-icons.scss 작성하는 방법**
    
    Jekyll Now에서 `_sass/_svg-icons.scss` 파일을 작성하는 방법은 다음과 같습니다. 이 파일은 SVG 아이콘의 스타일링을 담당하며, Jekyll 사이트에 통합하기 위해 필요합니다. 자세히 설명하겠습니다.
    
    - **1. 파일 생성**
        
        먼저, Jekyll 프로젝트의 `_sass` 디렉토리 안에 `_svg-icons.scss` 파일을 생성합니다.
        
    - **2. 기본 구조 작성**
        
        이제 `_svg-icons.scss` 파일에 필요한 기본 구조를 작성합니다. 일반적으로 SVG 아이콘을 정의하고 스타일링 하기 위해 사용됩니다.
        
        ```scss
        // _sass/_svg-icons.scss
        .icon {
          display: inline-block;
          fill: currentColor;
          height: 1em;
          vertical-align: middle;
          width: 1em;
        
          // Add default styles here
        }
        ```
        
        이 기본 구조는 SVG 아이콘을 포함하는 기본 클래스를 제공하며, 아이콘의 크기를 텍스트와 일치시키고 수직으로 정렬합니다. `fill: currentColor`는 아이콘의 색상을 텍스트 색상과 일치시키는 역할을 합니다.
        
    - **3. 특정 아이콘 스타일 추가**
        
        이제 특정 아이콘에 대한 스타일을 추가할 수 있습니다. 예를 들어, `home` 아이콘과 `search` 아이콘의 스타일을 정의할 수 있습니다.
        
        ```scss
        .icon-home {
          &:before {
            content: url('/path/to/home.svg');
          }
        }
        
        .icon-search {
          &:before {
            content: url('/path/to/search.svg');
          }
        }
        ```
        
        여기서 각각의 아이콘 클래스는 `content` 속성을 이용해 특정 SVG 파일의 경로를 설정합니다. 이렇게 함으로써 HTML에서 `.icon-home` 또는 `.icon-search` 클래스를 사용하면 해당 아이콘이 표시됩니다.
        
    - **4. 추가 스타일링**
        
        필요에 따라 각 아이콘에 대해 추가 스타일링을 할 수 있습니다. 예를 들어, 색상이나 크기를 변경할 수 있습니다.
        
        ```scss
        .icon-home {
          fill: blue;
        
          &:hover {
            fill: darkblue;
          }
        }
        
        .icon-search {
          fill: gray;
        
          &:hover {
            fill: black;
          }
        }
        ```
        
    - **5. HTML 파일에 통합**
        
        마지막으로, 정의한 클래스를 HTML 파일에서 사용하여 아이콘을 표시해야 합니다. 예를 들어:
        
        ```html
        <span class="icon icon-home"></span>
        <span class="icon icon-search"></span>
        ```
        
        이렇게 함으로써 CSS 파일에 정의한 스타일에 따라 아이콘이 표시됩니다.
        
    
    이와 같이 Jekyll Now 프로젝트에서 `_sass/_svg-icons.scss` 파일을 작성하고 사용하는 방법을 따라하면, SVG 아이콘을 효율적으로 스타일링하고 사용하여 프로젝트의 시각적 효과를 향상시킬 수 있습니다.
    
    ### **Jekyll Now _sass/_svg-icons.scss 적용 방법**
    
    Jekyll Now 테마에 `_sass/_svg-icons.scss` 파일을 적용하는 방법은 다음과 같습니다.
    
    - **1. SVG Icons 설정 파일 생성**
        
        우선, `_sass` 디렉토리에 `_svg-icons.scss` 파일을 생성하고, 해당 파일에 필요한 스타일을 추가합니다. 예를 들어 Mastodon 아이콘을 추가하려면 다음과 같이 작성할 수 있습니다.
        
        ```scss
        /* _sass/_svg-icons.scss */
        .mastodon {
            background-image: url('data:image/svg+xml;base64,여기에_아이콘의_base64_인코딩된_$바인딩_값을_추가합니다.');
            width: 24px; /* 아이콘의 넓이와 높이는 필요에 맞게 조정 */
            height: 24px;
            display: inline-block;
        }
        ```
        
    - **2. `_sass/_svg-icons.scss` 파일을 메인 SCSS 파일에 임포트**
        
        Jekyll Now의 메인 SCSS 파일에 `_svg-icons.scss` 파일을 임포트합니다. 일반적으로 메인 SCSS 파일은 `assets/css/style.scss` 또는 유사한 경로에 있을 것입니다. 메인 SCSS 파일에 다음을 추가합니다.
        
        ```scss
        @import "svg-icons";
        ```
        
    - **3. HTML 파일에서 아이콘 사용**
        
        이제 HTML 파일에서 해당 아이콘을 사용할 수 있습니다. 예를 들어, Footer에 Mastodon 아이콘을 추가하려면 다음과 같이 작성할 수 있습니다.
        
        ```html
        <footer>
            <a href="<https://mastodon.social/@yourusername>" class="mastodon"></a>
        </footer>
        ```
        
        이렇게 하면 `_sass/_svg-icons.scss`에 정의된 Mastodon 아이콘 스타일이 적용됩니다.
        
        위의 방법들을 통해 Jekyll Now 블로그에 커스텀 SVG 아이콘을 추가하고 사용할 수 있습니다. 추가적인 정보는 Jekyll Now 테마의 공식 GitHub 페이지에서도 확인할 수 있습니다.
        
        ‣
        
- **_variables.scss**
    - **CSS Code with Comments**
        
        ```css
        //
        // VARIABLES
        //
        
        // Colors
        $blue: #4183C4; /* 파란색 변수, #4183C4 색상 코드로 설정 */
        
        // Grays
        $black: #000; /* 검정색 변수, #000 색상 코드로 설정 */
        $darkerGray: #222; /* 더 어두운 회색 변수, #222 색상 코드로 설정 */
        $darkGray: #333; /* 어두운 회색 변수, #333 색상 코드로 설정 */
        $gray: #666; /* 중간 회색 변수, #666 색상 코드로 설정 */
        $lightGray: #eee; /* 밝은 회색 변수, #eee 색상 코드로 설정 */
        $white: #fff; /* 흰색 변수, #fff 색상 코드로 설정 */
        
        // Font stacks
        $helvetica: Helvetica, Arial, sans-serif; /* 기본 Helvetica 글꼴 스택, Helvetica가 없으면 Arial, Arial이 없으면 sans-serif 사용 */
        $helveticaNeue: "Helvetica Neue", Helvetica, Arial, sans-serif; /* "Helvetica Neue" 글꼴 스택, 없으면 Helvetica, Arial, sans-serif 사용 */
        $georgia: Georgia, serif; /* Georgia 글꼴 스택, Georgia가 없으면 serif 사용 */
        
        // Mobile breakpoints
        @mixin mobile {
          @media screen and (max-width: 640px) { /* 최대 너비 640px 이하의 화면에 대한 미디어 쿼리 */
            @content; /* 해당 미디어 쿼리 내에서 사용될 CSS 콘텐츠를 포함 */
          }
        }
        
        ```
        
    - **코드 내용과 의도 설명**
        
        이 CSS 코드는 SASS(또는 SCSS) 변수를 사용하여 색상, 글꼴 스택 및 모바일 브레이크포인트를 정의합니다. 이렇게 하면 코드의 재사용성과 유지보수성이 향상됩니다.
        
        - **Colors**: 색상을 변수로 정의하여 코드의 일관성을 유지하고, 나중에 색상을 변경할 때 용이하게 합니다.
        - **Grays**: 다양한 회색 음영을 변수로 정의하여 색상을 쉽게 재사용하고 관리할 수 있도록 합니다.
        - **Font stacks**: 다양한 글꼴 스택을 변수로 정의하여 코드의 가독성을 높이고, 여러 글꼴 옵션을 제공함으로써 브라우저 간 호환성을 높입니다.
        - **Mobile breakpoints**: `@mixin`과 `@media` 쿼리를 사용하여 반응형 디자인을 구현할 수 있도록 합니다.
    - **주요 용어**
        - **변수(Variable)**: CSS(SASS)에서 변수는 `$` 기호로 시작하며, 값(예: 색상, 글꼴 스택 등)을 저장하고 재사용할 수 있게 합니다.
        - **Mixin**: SASS의 기능 중 하나로, 여러 CSS 규칙을 하나로 묶어 재사용할 수 있게 합니다. `@mixin`을 사용하여 정의하고, `@include`를 사용하여 호출합니다.
        - **Media Query**: CSS에서 미디어 쿼리는 조건부 스타일을 지정할 수 있게 합니다. 특정 화면 크기 또는 장치 특성에 따라 다른 스타일을 적용할 수 있습니다.
    - **코드 사용 방법**
        - **색상 사용**: 변수를 사용하여 일관된 색상을 적용하고, 나중에 변수 값만 변경하면 전체 스타일에 영향을 미칩니다.
        - **글꼴 스택 사용**: 텍스트 요소에 글꼴을 지정할 때 변수를 사용하여 여러 글꼴 옵션을 제공하고, 일관된 스타일을 유지할 수 있습니다.
        - **미디어 쿼리 사용**: `@mixin`과 함께 사용하여 특정 화면 크기 이하에서만 적용되는 스타일을 정의할 수 있습니다.
    - **주의사항**
        - **유효한 색상 값 사용**: 색상 값을 정의할 때 항상 유효한 색상 코드(예: hex, RGB)를 사용해야 합니다.
        - **글꼴 스택 순서**: 글꼴 스택을 정의할 때 가장 우선적으로 사용하고자 하는 글꼴을 첫 번째로 두고, 대체 글꼴을 순차적으로 나열해야 합니다.
        - **미디어 쿼리**: 미디어 쿼리를 사용할 때는 여러 화면 크기를 고려하여 적절하게 설정해야 합니다.
    - **확장 가능성**
        - **변수 추가**: 더 많은 색상, 글꼴 또는 기타 스타일 속성을 변수로 정의하여 코드의 재사용성을 높일 수 있습니다.
        - **믹스인 추가**: 복잡한 스타일 규칙을 반복적으로 사용할 경우, 새로운 `@mixin`을 정의하여 코드의 중복을 줄이고 유지보수성을 높일 수 있습니다.
        - **반응형 디자인**: 다양한 화면 크기를 지원하기 위해 추가적인 미디어 쿼리를 사용하여 더욱 세부적인 반응형 스타일을 정의할 수 있습니다.
        
        이와 같은 방식으로 CSS 변수를 활용하면 스타일시트의 일관성을 유지하고, 유지보수가 쉬워집니다. 또한, 반응형 디자인을 통해 다양한 장치에서 일관된 사용자 경험을 제공할 수 있습니다.
