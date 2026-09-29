# 거상창업가이드

퇴사 전 준비부터 첫 매출까지, 창업 단계 진단·실무 양식·공식 지원 경로·창업노트를 제공하는 한국어 다페이지 웹사이트입니다.

## 실행

별도 패키지 설치 없이 정적 파일로 실행됩니다.

```powershell
python -m http.server 4173 --bind 127.0.0.1 --directory dist
```

브라우저에서 `http://127.0.0.1:4173/`을 여세요. 각 경로에는 직접 접속 가능한 `index.html`이 생성되어 있습니다.

## 주요 파일

- `dist/index.html`: 공통 HTML 셸과 헤더·푸터
- `site.config.json`: 브랜드명·기본 제목·설명을 관리하는 공통 설정
- `dist/styles.css`: 전체 디자인과 반응형 스타일
- `dist/home-refresh.css`: 메인 화면의 생애주기 그래프, 단계 탐색, 자료 미리보기, 이야기 섹션 스타일
- `dist/samantha.css`: 사만다·모니카 공통 안내, 로드맵 허브·상세 화면의 반응형 스타일
- `public/assets/personas/`: 상황 선택 카드의 원본 PNG와 640px WebP·AVIF 최적화 이미지
- `public/assets/samantha/`: 사만다 단독 인물 원본 PNG와 640px WebP·AVIF 최적화 이미지
- `public/assets/monica/`: 모니카 단독 인물 원본 PNG와 WebP·AVIF 최적화 이미지
- `dist/app.js`: 콘텐츠 데이터, 라우팅, 진단, 검색, 필터, 브라우저 저장
- `dist/downloads/`: XLSX·DOCX 빈 양식과 가상 작성 예시 40개
- `tools/build-sheets.mjs`, `tools/build-docs.py`: 양식 생성 스크립트
- `build-static.mjs`: 다페이지 진입 파일과 sitemap/robots 생성
- `CONTENT_GUIDE.md`: 운영 콘텐츠 수정 안내

## 다시 생성

브랜드명은 `site.config.json`에서 관리합니다. 양식이나 경로를 수정한 뒤 생성 스크립트를 실행하고 `node build-static.mjs`를 실행합니다. `dist`가 최종 배포 디렉터리입니다.

`build-static.mjs`는 `public/assets`를 `dist/assets`로 복사합니다. 상황 선택 카드와 두 안내자 컴포넌트는 AVIF·WebP를 우선 표시하고 원본 PNG를 대체 형식으로 사용합니다. 사만다와 모니카는 각각 전체 인물과 작은 아바타 파생 파일을 사용합니다.

메인 화면은 상황 선택 → 생애주기 준비 → 7단계 실행 패널 → 공식 지원 경로 → 실제 양식 미리보기 → 실전 이야기 순서로 구성됩니다. `사만다의 준비 가이드`는 판단·순서·조건 확인을, `모니카의 실행 팁`은 서류·고객·마케팅 실행을 안내합니다. 대표 환영·진단 결과·재도전에서는 두 안내자를 함께 표시하고, 각 페이지는 같은 공통 컴포넌트와 설정을 재사용합니다. 단계 탭 탐색은 저장된 진단 결과를 변경하지 않으며, 진단 결과는 기존 `gs-navi` 로컬 저장 키에 유지됩니다.
