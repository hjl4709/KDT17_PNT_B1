# KDT17_B1

이차전지 설비 제작·납품 기업을 위한 **CELLINK PLM** 팀 프로젝트입니다. 롤투롤 설비를 중심으로 프로젝트 일정·이슈와 기본 PLM 정보를 관리합니다.

- 팀 저장소: https://github.com/hjl4709/KDT17_PNT_B1
- 공유 사이트: https://cellink-plm-1103.candidhawk9.chatgpt.site
- 팀원 개발 방법: [CONTRIBUTING.md](CONTRIBUTING.md)

## 바로 실행하기

Node.js 22 이상(팀 기본 24)에서 다음 명령을 실행합니다. 현재 추가 설치가 필요한 패키지는 없습니다.

```bash
git clone https://github.com/hjl4709/KDT17_PNT_B1.git
cd KDT17_PNT_B1
npm run dev
```

`http://127.0.0.1:4173`을 열고 **체험 시작하기**를 누릅니다.

검사:

```bash
npm run check
```

## 구현된 기능

- 현장용 큰 글씨 화면 / 관리용 상세 화면
- 프로젝트 등록·수정, 내수·수출 구분
- 간트 차트, 작업 진행률, 지연 계산, 선행 작업 연결
- 이슈 등록·상태 변경·담당자 및 분류 필터, 목록·보드
- 표준 Excel/CSV 다중 파일 가져오기, 미리보기·검증
- 데이터 기반 주간 보고 초안, 편집·저장·엑셀 출력
- 도면·문서 개정 이력, 첨부파일, 부품 구성(BOM), 설계 변경 검토
- 브라우저 저장 및 JSON 백업·복원

## 폴더 구조

```text
cellink-plm/
  dist/
    index.html
    style.css
    app.js
    vendor/
  tests/smoke.mjs
scripts/serve.mjs
.github/workflows/check.yml
CONTRIBUTING.md
package.json
```

## 팀 공동 개발

각자 작업 브랜치를 만들고 Pull Request로 검토 후 `master`에 반영합니다. GitHub에 올린 변경과 Pull Request에는 기본 검사가 실행되도록 설정했습니다. 직접 push할 팀원은 저장소 관리자가 Collaborator로 초대해야 합니다.

**현재 GitHub 변경은 공유 사이트에 자동 배포되지 않습니다.** 현재 배포 주소의 갱신은 별도 배포 작업이 필요합니다.

## 현재 버전의 범위

가상 데이터 기반의 프런트엔드 체험 버전입니다. 입력 데이터와 첨부파일은 **사용 중인 브라우저에 저장**되며 직원 간 자동 공유되지 않습니다. 화면 모드는 편의 설정이며 권한이 아닙니다. 실제 사내 로그인·공용 DB·역할별 권한·AI API는 아직 연결하지 않았습니다. 주간 요약은 데이터 계산 기반이며 메모 추출은 키워드 규칙 기반입니다.

진행률은 등록 작업의 단순 평균입니다. 종료일이 오늘보다 이전이고 진행률이 100% 미만이면 지연입니다. 서로 다른 임의 양식의 엑셀을 자동 해석하지 않으며 표준 열 이름을 사용합니다.

원본 제안서 PDF, 개인 호스팅 설정, 로컬 Git 백업과 배포 압축파일은 이 저장소에 포함하지 않습니다.

## 오픈소스 라이브러리

- Frappe Gantt 1.0.4: MIT
- SheetJS CE 0.18.5: Apache-2.0

라이선스 원문은 `cellink-plm/dist/vendor/`에 포함되어 있습니다. 자세한 구현 범위는 [사이트 README](cellink-plm/README.md)를 참고하세요.
