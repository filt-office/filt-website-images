# filt-website-images (공개)

filt.kr에 나오는 사진을 웹용으로 줄여 둔 저장소입니다. GitHub Pages로 서비스됩니다:
https://filt-office.github.io/filt-website-images/

**손으로 고치지 않습니다.** 원본 비공개 저장소 filt-office/filt-website-editor의 게시 워크플로가 씁니다.
구조와 작업 규칙은 그 저장소의 `README.md`, `AGENTS.md`를 보세요.

## 어떻게 채워지나

- 빌더의 **게시**가 원본 `runtime/assets/<폴더>/<PC|MOB>/<파일>`을 줄여서 이곳 `assets/<폴더>/<PC|MOB>/<파일>`에 씁니다(`scripts/publish-images.js`).
  - 사진: PC 긴 변 2560px, MOB 긴 변 1600px(디자인 시스템 '게시 사진' 값). SVG·GIF·글꼴은 그대로 복사합니다.
  - 대상: `works`, `pages`, 그리고 게시용 JSON(`runtime/projects/<id>.json`)이 있는 프로젝트 폴더만.
- 템플릿(filt-office/filt-website)은 데이터의 `assets/…` 경로를 이 사이트 주소로 바꿔 불러옵니다.
- WORKS 썸네일은 데이터에 PC 경로만 있고, 모바일은 같은 이름의 `MOB/` 파일을 씁니다.

## 폴더

| 폴더 | 내용 |
|---|---|
| `assets/<프로젝트 ID>/PC`, `/MOB` | 상세 페이지 사진·도면 |
| `assets/works/PC`, `/MOB` | WORKS 목록·갤러리 썸네일 |
| `assets/pages/PC` | HOME·OFFICE·NEWS 이미지, 디자인 시스템 글꼴 |
| `.published.json` | 파일별 원본 해시. 바뀌지 않은 사진은 다시 변환하지 않음 |

파일 이름은 원본 그대로입니다. `09842e6973165.jpg` 같은 이름은 옛 아임웹 이미지 이름을 그대로 가져온 것입니다.

## 지우기

- 게시는 이곳 파일을 **지우지 않습니다**. 이전 게시본으로 되돌려도 사진이 남아 있게 하기 위해서입니다.
- 안 쓰는 사진 정리는 사용자가 고른 것만, 현재 게시본에서 안 쓰이는 것이 확인된 것만 지웁니다. 지울 때 `.published.json`의 해당 항목도 함께 지웁니다.
