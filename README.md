# Minecraft 기본 블록 튜토리얼 모음

Minecraft Education Edition의 기본 블록만 사용하는 튜토리얼 모음입니다.

## 📚 튜토리얼 목록

### 01. 채팅 기초 (Basic Chat)
- 채팅 이벤트 처리
- 플레이어에게 메시지 표시
- 간단한 명령어 만들기

### 02. 건축 기초 (Building Basics)
- 블록 배치하기
- 블록 채우기
- 간단한 구조물 만들기

### 03. 도형 그리기 (Shapes)
- 원, 선, 사각형 그리기
- 좌표 계산
- 복잡한 패턴 만들기

### 04. 몹 생성 (Mobs)
- 몹 생성하기
- 몹 종류 선택
- 여러 몹 동시에 생성

## 🎮 사용 방법

### 로컬에서 개발
1. 원하는 튜토리얼 폴더로 이동
2. `pxt.json` 파일 확인
3. `tutorial.md` 파일 편집

### 새 튜토리얼 추가
```bash
mkdir tutorials/05-새튜토리얼
cd tutorials/05-새튜토리얼
# pxt.json과 tutorial.md 작성
```

## 📖 기본 블록 카테고리

### Player (플레이어)
- `player.onChat()` - 채팅 이벤트
- `player.say()` - 메시지 표시
- `player.position()` - 플레이어 위치

### Blocks (블록)
- `blocks.place()` - 블록 배치
- `blocks.fill()` - 영역 채우기
- `blocks.clone()` - 블록 복제

### Positions (좌표)
- `pos()` - 좌표 생성
- `positions.add()` - 좌표 더하기

### Shapes (도형)
- `shapes.circle()` - 원 그리기
- `shapes.line()` - 선 그리기
- `shapes.sphere()` - 구 그리기

### Mobs (몹)
- `mobs.spawn()` - 몹 생성

### Gameplay (게임플레이)
- `gameplay.timeSet()` - 시간 설정
- `gameplay.setWeather()` - 날씨 변경

## 🔧 파일 구조

```
makecodetutorial/
├── README.md
├── tutorials/
│   ├── 01-basic-chat/
│   │   ├── pxt.json
│   │   └── tutorial.md
│   ├── 02-building-basics/
│   │   ├── pxt.json
│   │   └── tutorial.md
│   ├── 03-shapes/
│   │   ├── pxt.json
│   │   └── tutorial.md
│   └── 04-mobs/
│       ├── pxt.json
│       └── tutorial.md
```

## 📝 라이센스

MIT License
