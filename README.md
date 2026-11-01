# S2

한 레포에서 두 게임을 GitHub Pages로 각각 다른 주소에 배포합니다.

| 폴더 | 내용 | 배포 주소 |
| --- | --- | --- |
| [`hangawi/`](hangawi/) | 한가위 이야기 아케이드 (추석 계기교육 웹게임, 단일 HTML) | https://gmeann.github.io/S2/ |
| [`toegeungil-school/`](toegeungil-school/) | 퇴근길 학교 (초등 선생님을 위한 3D 쉼터, Vite + React + three) | https://gmeann.github.io/S2/toegeungil-school/ |

- 배포는 `.github/workflows/deploy.yml` 이 두 폴더를 한 사이트로 합쳐서 올립니다.
- 퇴근길 학교 실행 방법은 [`toegeungil-school/README.md`](toegeungil-school/README.md)를 보세요.
- 한가위 게임은 `hangawi/index.html` 을 브라우저로 바로 열어도 됩니다.
