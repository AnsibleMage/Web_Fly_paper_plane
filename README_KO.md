# 종이비행기 날아라 (Fly Paper Plane)

> React와 Three.js로 만든 3D 웹 종이비행기 비행 게임 - 타임어택 챌린지

## 개요

종이비행기 날아라는 로블록스 스타일의 3D 비행 게임입니다. 종이비행기를 조종하여 장애물을 피하고 최단 시간 내에 골 지점에 도달하는 타임어택 게임으로, 실시간 물리 시뮬레이션, 3인칭 카메라 시스템, 이메일 기반 인증, 글로벌 리더보드를 제공합니다.

## 주요 기능

### 게임 플레이
- **직관적인 비행 조작**: WASD 키로 상하좌우 이동, Shift로 부스트
- **3D 환경**: Three.js와 React Three Fiber 기반 몰입감 있는 3D 그래픽
- **장애물 회피**: 나무, 건물 등 다양한 장애물 피하기
- **타임어택 모드**: 최단 시간으로 골 지점 도달
- **실시간 카메라**: 비행기를 추적하는 3인칭 시점

### 소셜 기능
- **이메일 인증**: 간단한 이메일 기반 로그인 시스템
- **리더보드**: 전체 플레이어 순위 시스템
- **기록 관리**: 개인 최고 기록 추적 및 저장

### UI/UX
- **메인 메뉴**: 게임 시작, 리더보드, 설정
- **게임 HUD**: 실시간 타이머, 속도계
- **결과 화면**: 게임 완료 후 기록 표시 및 저장
- **사운드 시스템**: 배경음악 및 효과음

## 조작법

| 키 | 동작 |
|----|------|
| **W** | 상승 |
| **S** | 하강 |
| **A** | 좌측 이동 |
| **D** | 우측 이동 |
| **Shift** | 부스트 (속도 증가) |

## 기술 스택

| 구분 | 기술 |
|------|------|
| **UI 프레임워크** | React 18, TypeScript |
| **3D 렌더링** | Three.js, @react-three/fiber, @react-three/drei |
| **물리 엔진** | cannon-es (비행), @react-three/rapier (충돌) |
| **상태 관리** | Zustand |
| **스타일링** | Tailwind CSS |
| **애니메이션** | Framer Motion |
| **폼** | React Hook Form + Zod |
| **빌드 도구** | Vite |
| **테스트** | Vitest, Testing Library, Playwright, Stryker (변이 테스트) |

## 시작하기

### 필수 조건
- Node.js v18.0 이상
- npm

### 설치

```bash
git clone https://github.com/AnsibleMage/Web_Fly_paper_plane.git
cd Web_Fly_paper_plane
npm install
```

### 실행

```bash
# 개발 서버 (http://localhost:5173)
npm run dev

# 프로덕션 빌드
npm run build

# 빌드 미리보기
npm run preview
```

## 프로젝트 구조

**4-Layer 프랙탈 아키텍처** 기반으로 Block, Feature, Task로 구성됩니다:

```
1 Product = 4 Blocks = 14 Features = 70 Tasks
```

```
src/
├── blocks/
│   ├── block1-flight-control/     # 비행 물리, 입력, 카메라
│   │   └── features/
│   │       ├── f1-input-handler/      # 키보드 & 마우스 입력
│   │       ├── f2-flight-physics/     # 물리 엔진 & 역학
│   │       └── f3-camera-system/      # 카메라 추적 & 제약
│   ├── block2-game-core/          # 코스, 타이머, 충돌
│   │   └── features/
│   │       ├── f1-course-manager/     # 코스 정의 & 체크포인트
│   │       ├── f2-timer-record/       # 타이머 & 기록 관리
│   │       └── f3-collision-state/    # 충돌 감지 & 게임 상태
│   ├── block3-social/             # 인증, 리더보드, 기록
│   │   └── features/
│   │       ├── f1-email-auth/         # 이메일 검증 & 인증
│   │       ├── f2-leaderboard-display/ # 순위표 & 표시
│   │       └── f3-record-manager/     # 기록 제출 & 저장
│   └── block4-ui-ux/             # 메뉴, HUD, 사운드 (진행 중)
│       └── features/
│           ├── f1-main-menu/
│           ├── f2-game-hud/
│           ├── f3-result-screen/
│           ├── f4-3d-environment/
│           └── f5-sound-effects/
├── components/                    # 공유 React 컴포넌트
├── hooks/                         # 커스텀 React hooks
└── App.tsx                        # 메인 애플리케이션 진입점
```

## 테스트

```bash
# 단위 테스트 (watch 모드)
npm test

# 테스트 커버리지 (목표: >90%)
npm run test:coverage

# 변이 테스트 (목표: >80%)
npm run test:mutation

# E2E 테스트
npm run test:e2e

# E2E 테스트 (헤드리스 모드)
npm run test:e2e:headed
```

### 테스트 현황

| Block | 테스트 수 | 상태 |
|-------|-----------|------|
| Block 1 - 비행 제어 | 454 | 완료 |
| Block 2 - 게임 코어 | 204 | 완료 |
| Block 3 - 소셜 | 183 | 완료 |
| Block 4 - UI/UX | 6 | 진행 중 |
| **합계** | **847** | **64% 완료** |

## 개발 방법론

**4-Layer 프랙탈 TDD + 피라미드 워크플로우** 기반:

```
Task 단위 테스트 -> Feature 통합 테스트 -> Block 모듈 테스트 -> Product E2E 테스트
```

핵심 원칙:
- **TDD**: Red -> Green -> Refactor -> Mutation
- **피라미드 워크플로우**: 하위 레이어 완료 후 상위 레이어 통합
- **추측 배제 프로토콜(Zero-Guess)**: 모든 코드는 명세 문서에서 도출

## 성능 목표

| 지표 | 목표 |
|------|------|
| 초기 로딩 | < 3초 |
| FPS | >= 60 |
| 입력 응답 | < 16ms |
| 리더보드 조회 | < 1초 |

## 문서

- `doc/Product_PRD_*.md` -- 제품 요구사항 명세서
- `doc/CJ_AI_*.md` -- 개발 방법론 가이드
- `doc/LAUNCH_ROADMAP.md` -- 런칭 로드맵

## 라이선스

MIT

---

*React, Three.js 그리고 Claude Code로 AnsibleMage가 제작*
