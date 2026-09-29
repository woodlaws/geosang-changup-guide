# 거상 창업내비

퇴사 전 준비부터 첫 매출까지 창업 단계 진단, 실무 양식, 공식 지원 경로와 개인 창업노트를 제공하는 한국어 다페이지 사이트입니다.

## GitHub + Vercel 배포

1. 이 폴더의 **내용 전체**를 새 GitHub 저장소의 최상위 경로에 올립니다.
2. Vercel에서 **Add New → Project**를 선택합니다.
3. 해당 GitHub 저장소를 Import합니다.
4. Framework Preset은 **Other**로 확인합니다.
5. 별도 환경변수 없이 Deploy를 실행합니다.

`vercel.json`이 현재 폴더 전체를 정적 출력으로 지정합니다. GitHub 저장소가 Vercel에 연결되면 `main` 브랜치 변경은 운영 배포로, 다른 브랜치와 Pull Request는 미리보기 배포로 생성됩니다.

자세한 내용은 [DEPLOY.md](DEPLOY.md)를 참고하세요.

## 로컬 확인

```bash
python -m http.server 4173
```

브라우저에서 `http://127.0.0.1:4173/`을 엽니다.

## 주요 구조

- `index.html`, `styles.css`, `app.js`: 사이트 공통 화면과 기능
- `roadmap/`, `resources/`, `support/`, `stories/`: 직접 접속 가능한 하위 페이지
- `downloads/`: XLSX·DOCX 빈 양식과 가상 작성 예시 40개
- `vercel.json`: Vercel 정적 배포 설정
- `.github/workflows/validate.yml`: GitHub Push/PR 기본 검증

문의 수신 서버와 운영 도메인은 아직 연결되어 있지 않습니다.
