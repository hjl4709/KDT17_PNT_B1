# 팀원 개발 안내

팀 저장소: https://github.com/hjl4709/KDT17_PNT_B1

## 처음 시작하기

1. Node.js 22 이상을 준비합니다. 팀 기본 환경은 Node.js 24입니다.
2. 저장소를 내려받습니다.

```bash
git clone https://github.com/hjl4709/KDT17_PNT_B1.git
cd KDT17_PNT_B1
npm run dev
```

3. 터미널에 나온 `http://127.0.0.1:4173`을 엽니다.
4. ‘체험 시작하기’를 눌러 관리용 화면 또는 현장용 화면을 확인합니다.

현재 버전은 추가 패키지 설치 없이 실행됩니다. 로컬 미리보기에서는 Sites의 ChatGPT 로그인을 사용하지 않고 ‘체험 시작하기’를 사용합니다.

## 변경하는 순서

각자 작업 브랜치를 만들어 수정하고, GitHub의 Pull Request에서 팀원에게 검토를 요청합니다.

```bash
git switch master
git pull --ff-only origin master
git switch -c feature/작업이름
```

파일을 수정한 뒤 확인합니다.

```bash
npm run check
git add 수정한파일경로
git commit -m "변경 내용 설명"
git push -u origin feature/작업이름
```

GitHub에서 `feature/작업이름` → `master`로 Pull Request를 만들고, 검토 후 합칩니다. 다른 사람의 변경 이력을 덮어쓰는 강제 푸시는 사용하지 않습니다. `master`가 팀 공통 기준입니다.

저장소에 직접 push하려면 관리자가 팀원을 Collaborator로 초대해야 합니다. 공개 저장소이므로 초대 전에도 누구나 내려받을 수 있고, 저장소를 Fork한 뒤 Pull Request를 보낼 수 있습니다.

## 주요 파일

| 파일 | 역할 |
|---|---|
| `cellink-plm/dist/index.html` | 페이지 진입점 |
| `cellink-plm/dist/style.css` | 화면 디자인·반응형·큰 글씨 모드 |
| `cellink-plm/dist/app.js` | 화면, 업무 동작, 브라우저 저장, 엑셀 가져오기 |
| `cellink-plm/tests/smoke.mjs` | 계산·입력 검증·엑셀 읽기 검사 |
| `scripts/serve.mjs` | 로컬 미리보기 서버 |

## 함께 확인할 사항

- 현장용 화면에서 큰 글씨·버튼과 ‘내 작업’ 흐름을 확인합니다.
- 진행률 변경 후 지연 집계와 프로젝트 현황이 맞는지 확인합니다.
- 이슈 등록·상태 변경, 주간 보고서 저장, 표준 엑셀 가져오기를 확인합니다.
- 실제 고객 정보·도면·비밀번호·개인 설정은 공개 저장소에 올리지 않습니다.

## 배포와 데이터 공유

공유 사이트: https://cellink-plm-1103.candidhawk9.chatgpt.site

GitHub에 소스를 수정해 올리는 것과 사이트 배포는 별도입니다. 현재 GitHub 변경이 공유 사이트에 자동 반영되지는 않습니다. 배포 자동화는 이후에 연결합니다.

입력 데이터와 첨부파일은 각자의 브라우저에 저장됩니다. GitHub에서 같은 소스를 받아도 업무 데이터가 서로 공유되지는 않습니다. 실제 다중 사용자 업무에는 로그인·공용 DB·서버 권한 검증이 추가로 필요합니다.
