# Koinonia Archive · 코이노니아 아카이브

> **All is Yours** — 내가 가진 모든 지식과 자료가 곧 당신의 것

서버 없이 동작하는 **단일 HTML 파일**로 만든 자료 공유 홈페이지입니다. GitHub Pages, Cloudflare Pages, Netlify 등 어떤 정적 호스팅에도 그대로 올릴 수 있습니다.

## 기능

- 한국어 / English 전환
- 실시간 검색(일치 강조), 카테고리·형식 필터, 최신·인기·제목순 정렬, 격자/목록 보기
- 자료 상세: 다운로드, 미리보기, 링크 복사, 조회·다운로드 수, 비슷한 자료
- 회원가입 / 로그인, 회원 전용 자료, 즐겨찾기
- 자료 요청 폼
- 관리자 콘솔: 대시보드, 자료 CRUD(한/영), 카테고리, 회원, 요청함, 사이트 설정, 백업·배포

## 빠른 시작

1. 이 저장소를 Fork 하거나 내려받습니다.
2. 공유할 파일을 `files/` 폴더에 넣습니다.
3. `index.html`을 열고 오른쪽 위 **로그인** → 이메일 `admin`, 비밀번호 `admin1234`로 관리자에 들어갑니다.
4. **사이트 설정**에서 이름·이메일·관리자 비밀번호를 바꿉니다.
5. **자료 관리**에서 자료를 추가하고, **백업·배포 → index.html 내려받기**로 완성본을 받아 저장소의 `index.html`을 교체합니다.
6. GitHub → Settings → Pages → Branch `main` / (root) → Save. 1~2분 뒤 `https://<아이디>.github.io/<저장소명>/`에서 열립니다.

## 구조

```
index.html   # 사이트 전체 (HTML + CSS + JS + 초기 데이터)
files/       # 공유 파일 (PDF, HTML, DOCX …)
LICENSE
README.md
```

데이터는 `index.html` 안의 `<script id="seed">` JSON 블록에 들어 있고, 관리자 콘솔이 이 블록을 갱신한 배포용 파일을 만들어 줍니다. 방문자의 회원 정보와 요청은 각자의 브라우저(localStorage)에 저장됩니다. 모든 기기의 데이터를 한곳에 모으려면 `save()`, `load()`, 회원가입·로그인 함수에 Supabase 같은 백엔드를 연결하면 됩니다.

## 라이선스

- 코드: [MIT](LICENSE)
- 글꼴: Inter, Noto Sans KR, Noto Serif KR — SIL Open Font License 1.1 (Google Fonts에서 로드)
- 공유 자료(`files/`): 별도 표기가 없으면 CC BY 4.0

외부 라이브러리, 아이콘 팩, 이미지, 템플릿을 사용하지 않았습니다. 아이콘은 모두 직접 그린 인라인 SVG이며, 이모지는 방문자 기기의 시스템 글꼴로 표시됩니다.
