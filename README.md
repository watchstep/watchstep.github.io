## Watchstep's Resume

- 영문: https://watchstep.site/
- 국문: https://watchstep.site/kr

Jekyll로 만든 한 페이지 이력서. [crispgm/resume](https://github.com/crispgm/resume/tree/master) 테마 기반.

### 이력 수정하기

내용은 모두 두 데이터 파일에 있다. 레이아웃은 건드릴 필요 없다.

| 파일 | 페이지 |
| --- | --- |
| `_data/resume/kr.yml` | 국문 `/kr` |
| `_data/resume/en.yml` | 영문 `/` |

- 두 파일은 구조가 같다. 항목을 추가하거나 고칠 때는 두 파일을 같이 수정한다.
- 목록 순서대로 화면에 나온다. 최신 항목을 맨 위에 넣는다.
- 값에 `<b>굵게</b>` 같은 HTML을 쓸 수 있다. `:`가 들어간 문장은 `"..."`로 감싼다.
- 섹션 제목(Skill, Career, Education, Experience, Project)은 두 언어 모두 영어로 고정이며 `_layouts/resume.html`에 있다.

#### Career / Experience / Project

세 섹션은 같은 필드를 쓴다. `title`과 `duration` 외에는 모두 선택이다.

```yaml
career:
  - title: AI 엔지니어            # 직무 / 활동명 / 프로젝트명
    org: 진학사 (캐치)            # 소속. 있으면 "title @ org"로 표시
    url: https://...              # 있으면 제목 옆에 링크 아이콘 표시
    duration: 2025.01 - 현재
    about: 연세대학교 인공지능 학회  # 기간 옆에 "기간 | about"으로 표시
    description: 한두 문장 소개
    highlights:                   # 줄마다 "• "로 표시
      - 주요 성과 1
      - 주요 성과 2
```

#### Education / Skill / Contact

```yaml
education:
  - university: 연세대학교
    duration: 2020.03 - 2025.02
    location: 서울
    major: 문헌정보학 · 응용통계학 복수전공

skill:
  - title: 프로그래밍 언어
    items: Python, R, Dart

contact:
  - name: github      # 아이콘 이름. _includes/svg.html에 있는 이름 (email, github, linkedin, kakaotalk 등)
    url: https://github.com/watchstep
```

### 로컬 미리보기

1. Ruby 설치 (macOS: `brew install ruby`, Windows: [RubyInstaller](https://rubyinstaller.org/downloads/))
2. 의존성 설치
```
bundle config set --local path vendor/bundle
bundle install
```
3. 실행 후 `localhost:4000`(영문), `localhost:4000/kr`(국문) 확인
```
bundle exec jekyll serve
```

### 배포

`main` 브랜치에 push하면 GitHub Pages가 자동으로 빌드한다. `_site/`는 빌드 결과물이므로 커밋하지 않는다.

### 디자인 수정

- 색상: `css/resume.css` 맨 위 `:root` 변수. 포인트 색상은 `--accent` 한 줄만 바꾸면 된다.
- 폰트: 영문은 Literata. 국문은 섹션 제목과 하단 footer만 Literata, 나머지는 Noto Sans KR.
  `css/resume.css`의 `html[lang="ko"]` 규칙과 `_includes/header.html`의 폰트 링크에서 바꾼다.
- PDF: 페이지 하단 `PDF` 링크로 브라우저 인쇄.

### 구조

```
_data/resume/kr.yml, en.yml   이력 내용
index.html                    영문 페이지 (/)
kr/index.html                 국문 페이지 (/kr)
_layouts/resume.html          섹션 구성
_includes/entry.html          Career/Experience/Project 항목 하나
_includes/header.html         <head>, 폰트
_includes/svg.html            아이콘
css/resume.css                스타일
```

---
For more details, refer to the [Jekyll docs](https://jekyllrb.com/docs/)
