# GitHub·Vercel 배포 안내

## 1. GitHub 저장소 만들기

GitHub에서 빈 저장소를 만든 뒤 이 폴더 안의 파일과 폴더를 저장소 최상위에 업로드합니다. 압축파일 자체를 저장소에 올리지 말고, 압축을 푼 **내용물**을 올리세요.

권장 기본 브랜치는 `main`입니다. `.vercel` 폴더와 로그 파일은 `.gitignore`에서 제외됩니다.

## 2. Vercel에 연결하기

1. Vercel 대시보드에서 **Add New → Project**를 선택합니다.
2. GitHub 저장소를 Import합니다.
3. Framework Preset은 **Other**로 선택하거나 자동 감지 결과가 Other인지 확인합니다.
4. Root Directory는 저장소 루트인 `.`을 사용합니다.
5. Build Command와 Install Command는 비워 둡니다.
6. Output Directory는 저장소의 `vercel.json`에 `.`으로 지정되어 있습니다.
7. Deploy를 실행합니다.

이 사이트는 외부 API 키가 필요하지 않습니다.

## 3. 배포 후 확인

- `/`, `/start/`, `/roadmap/validation/` 직접 접속
- `/resources/estimate/`에서 XLSX 다운로드
- 진단 결과가 새로고침 후 `/my/`에 유지되는지 확인
- 모바일 메뉴, 통합 검색, 지원 경로 필터 확인
- 운영 도메인 확정 후 `sitemap.xml`의 주소와 canonical 정책 보완

## 4. Git 연동 배포 방식

- `main` 브랜치 Push 또는 Merge: 운영 배포
- 다른 브랜치 Push: 미리보기 배포
- Pull Request: 변경사항 미리보기 배포

GitHub Actions의 `Validate static site` 작업은 자바스크립트 문법과 필수 파일을 검사합니다. 실제 배포는 Vercel Git 연동이 담당하므로 별도의 Vercel 토큰을 저장소에 넣지 않습니다.

## 5. 주의사항

- `.vercel` 폴더, Vercel 토큰, API 키를 Git에 올리지 마세요.
- 문의 화면은 현재 내용을 복사·다운로드하는 기능이며 서버 접수 기능이 아닙니다.
- 지원사업 정보는 공식 원문에서 모집 여부와 신청 조건을 최종 확인해야 합니다.
