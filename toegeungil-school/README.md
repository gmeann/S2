# 퇴근길 학교 (가칭)

초등 선생님을 위한 웹 기반 3D 쉼터예요. 로그인 없이 들어와서, 노을 진 운동장을 천천히 걸으며 쉬어 가는 공간입니다.

- Vite + React + TypeScript
- three, @react-three/fiber, @react-three/drei
- 서버·DB·외부 모델/텍스처 파일 없음. 모든 물체는 기본 도형으로 코드에서 만듭니다.
  (글꼴만 Pretendard 웹폰트를 CDN에서 불러오고, 실패하면 시스템 글꼴을 씁니다.)

## 실행 방법

Node.js 20 이상이 필요해요. 모든 명령은 **`toegeungil-school` 폴더 안에서** 실행합니다.

```bash
cd toegeungil-school
```

```bash
npm install
```

```bash
npm run dev
```

브라우저에서 `http://localhost:5173` 을 열면 됩니다.

### 폰으로 접속해 보기

PC와 폰이 **같은 와이파이**에 있어야 해요.

```bash
npm run dev -- --host
```

터미널에 나오는 `Network: http://192.168.x.x:5173/` 주소를 폰 브라우저에 입력하세요.

### 빌드 / 미리보기

```bash
npm run build
```

```bash
npm run preview
```

## 조작

- 바닥을 클릭(폰은 탭)하면 캐릭터가 그 지점으로 걸어가요.
- PC에서는 마우스 휠로 확대/축소할 수 있어요. 카메라 회전은 일부러 넣지 않았어요.

## 배포 (GitHub Pages)

`main` 또는 작업 브랜치(`claude/upbeat-ride-tpmm9s`)에 `toegeungil-school/` 변경을 푸시하면, 레포 루트의 `.github/workflows/deploy.yml` 이 이 폴더만 빌드해서 GitHub Pages에 올립니다. Actions 탭에서 **Run workflow** 로 직접 실행할 수도 있어요.

처음 한 번만 설정이 필요해요.

1. GitHub 레포 → **Settings → Pages**
2. **Build and deployment → Source** 를 **GitHub Actions** 로 선택
3. **Settings → Environments → github-pages → Deployment branches** 에 작업 브랜치(`claude/upbeat-ride-tpmm9s`)가 허용돼 있어야 해요. (기본값은 기본 브랜치만 허용)
4. 푸시하면 Actions 탭에서 진행 상황을 볼 수 있고, 끝나면 `https://<사용자명>.github.io/<레포이름>/` 에서 열립니다.

### 레포 이름(base 경로) 바꾸기

- 워크플로는 레포 이름을 자동으로 읽어서 `BASE_PATH=/<레포이름>/` 로 빌드해요. 레포 이름을 바꿔도 따로 고칠 것이 없어요.
- 직접 빌드할 때는 `vite.config.ts` 의 `REPO_NAME` 상수를 고치거나, 환경변수로 덮어쓰면 됩니다.

```bash
BASE_PATH=/my-repo/ npm run build
```

## 폴더 구조

```
toegeungil-school/src/
  components/  3D 물체(하늘, 바닥, 나무, 가로등, 벤치, 캐릭터, 카메라)와 HUD
  scenes/      장면 조립 (Playground = 운동장)
  hooks/       클릭 이동 + 충돌 처리 (useClickToMove)
  data/        이름표 목록, 운동장 배치·충돌 영역

```
