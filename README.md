# Minecraft 기본 블록 튜토리얼 모음

Minecraft Education Edition의 기본 블록만 사용하는 튜토리얼 모음입니다.

## 📚 튜토리얼 목록

### 01. 채팅 기초 (Basic Chat)
- 채팅 이벤트 처리
- 플레이어에게 메시지 표시
- 간단한 명령어 만들기

**웹 브라우저:**
```
https://minecraft.makecode.com/#tutorial:github:ssakspirit/makecodetutorial/tutorial-01-chat.md
```

**커맨드 블록:**
```
codebuilder navigate @p false https://minecraft.makecode.com/#tutorial:github:ssakspirit/makecodetutorial/tutorial-01-chat.md
```

### 02. Building Extension으로 건축하기
- Building Extension 사용법
- ㅁ형 건물 만들기
- 원형 건물 만들기
- 다양한 크기와 재료

**웹 브라우저:**
```
https://minecraft.makecode.com/#tutorial:github:ssakspirit/makecodetutorial/tutorial-02-building.md
```

**커맨드 블록:**
```
codebuilder navigate @p false https://minecraft.makecode.com/#tutorial:github:ssakspirit/makecodetutorial/tutorial-02-building.md
```

### 03. 도형 그리기 (Shapes)
- 원, 선, 사각형 그리기
- 좌표 계산
- 복잡한 패턴 만들기

**웹 브라우저:**
```
https://minecraft.makecode.com/#tutorial:github:ssakspirit/makecodetutorial/tutorial-03-shapes.md
```

**커맨드 블록:**
```
codebuilder navigate @p false https://minecraft.makecode.com/#tutorial:github:ssakspirit/makecodetutorial/tutorial-03-shapes.md
```

### 04. 몹 생성 (Mobs)
- 몹 생성하기
- 몹 종류 선택
- 여러 몹 동시에 생성

**웹 브라우저:**
```
https://minecraft.makecode.com/#tutorial:github:ssakspirit/makecodetutorial/tutorial-04-mobs.md
```

**커맨드 블록:**
```
codebuilder navigate @p false https://minecraft.makecode.com/#tutorial:github:ssakspirit/makecodetutorial/tutorial-04-mobs.md
```

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
├── README.md                      # 메인 설명서
├── pxt.json                       # MakeCode 프로젝트 설정
├── tutorial-01-chat.md            # 채팅 기초 튜토리얼
├── tutorial-02-building.md        # 건축 기초 튜토리얼
├── tutorial-03-shapes.md          # 도형 그리기 튜토리얼
└── tutorial-04-mobs.md            # 몹 생성 튜토리얼
```

## 📝 라이센스

MIT License
