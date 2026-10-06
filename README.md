# min-viewer

민법2 중간고사 노트 학습 뷰어의 **공개 껍데기**입니다. 이 레포에는 노트 내용이 없습니다.
노트와 기록(하이라이트·빈칸·메모·필기·별표·진도)은 비공개 레포 `chamcham02/min-mid`에 있고,
이 페이지는 기기마다 넣는 GitHub 토큰으로 그 비공개 레포에 접속해 노트를 열고 기록을 저장합니다.

**열기: https://chamcham02.github.io/min-viewer/**

## 처음 한 번(기기마다)
1. GitHub에 `chamcham02` 계정으로 로그인한 뒤 [새 토큰 만들기(Fine-grained)](https://github.com/settings/personal-access-tokens/new)를 엽니다.
2. Token name `min-viewer`, Expiration은 원하는 기간.
3. Repository access → **Only select repositories** → `chamcham02/min-mid`만 고릅니다.
4. Permissions → Repository permissions → **Contents: Read and write**.
5. Generate token → `github_pat_…` 토큰을 복사해 뷰어 첫 화면에 붙여 넣습니다.

아이패드는 Safari 공유 버튼 → **홈 화면에 추가**로 앱처럼 쓸 수 있습니다(홈 화면 앱은 Safari와 저장소가 따로라 토큰을 한 번 더 넣습니다).

## 동작
- `index.html`(이 껍데기)이 비공개 레포 `main` 브랜치의 최신 커밋을 확인해, 노트 페이지(`index.html`)를 바뀐 경우에만 받아 기기에 보관한 뒤 엽니다. 인터넷이 없으면 보관본으로 엽니다(`sw.js`가 이 껍데기를 오프라인용으로 저장).
- 기록은 비공개 레포 `data` 브랜치의 `data/minbeop2-midterm.json`에 저장됩니다. 바뀐 기록은 몇 초 안에 올라가고, 다른 기기의 변경은 20초마다·화면으로 돌아올 때 받아 합칩니다.
- 이 레포에 있는 것은 연결 정보(`index.html`의 `SRC`)와 껍데기 화면뿐입니다.

## 보안
- 토큰은 그 기기 브라우저의 저장소(localStorage, `chamcham02.github.io`)에만 저장되고 GitHub API로만 보냅니다.
- 토큰 권한은 `chamcham02/min-mid`의 Contents 읽기·쓰기뿐이라, 다른 레포나 계정 설정에는 쓸 수 없습니다.
- 같은 `chamcham02.github.io` 주소에 다른 GitHub Pages 사이트를 만들면 그 사이트의 스크립트도 이 저장소를 읽을 수 있으니, 믿을 수 없는 코드는 올리지 마세요.
- 기기를 잃어버렸거나 토큰이 새었다면 [토큰 목록](https://github.com/settings/personal-access-tokens)에서 지우면 바로 막힙니다. 뷰어의 설정(⋯) → **이 기기 연결 끊기**는 그 기기에서만 토큰을 지웁니다.
