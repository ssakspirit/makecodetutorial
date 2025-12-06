# MakeCode 튜토리얼 프로젝트 만들기 가이드

이 문서는 Minecraft Education Edition용 MakeCode 튜토리얼을 GitHub에 올려서 사용하는 방법을 설명합니다.

## 📋 목차

1. [프로젝트 구조 이해하기](#1-프로젝트-구조-이해하기)
2. [필수 파일 생성하기](#2-필수-파일-생성하기)
3. [튜토리얼 작성하기](#3-튜토리얼-작성하기)
4. [GitHub에 업로드하기](#4-github에-업로드하기)
5. [튜토리얼 사용하기](#5-튜토리얼-사용하기)
6. [문제 해결](#6-문제-해결)

---

## 1. 프로젝트 구조 이해하기

### 최종 파일 구조

```
makecodetutorial/
├── pxt.json                    # MakeCode 프로젝트 설정 파일 (필수)
├── README.md                   # 프로젝트 설명 (권장)
├── GUIDE.md                    # 이 가이드 문서
├── tutorial-01-chat.md         # 튜토리얼 1
├── tutorial-02-building.md     # 튜토리얼 2
├── tutorial-03-shapes.md       # 튜토리얼 3
└── tutorial-04-mobs.md         # 튜토리얼 4
```

### 핵심 개념

- **pxt.json**: MakeCode가 프로젝트를 인식하는 메타데이터 파일
- **tutorial-*.md**: 실제 튜토리얼 내용 (Markdown 형식)
- **루트 위치**: 모든 튜토리얼 파일은 저장소 루트에 있어야 함 (서브폴더 불가)

---

## 2. 필수 파일 생성하기

### 2.1 pxt.json 만들기

프로젝트 루트에 `pxt.json` 파일을 생성합니다.

```json
{
    "name": "basic-tutorials",
    "version": "2.0.0",
    "description": "Minecraft 기본 블록 및 Building Extension 튜토리얼 모음",
    "license": "MIT",
    "dependencies": {
        "core": "*",
        "builder": "*",
        "building": "github:ssakspirit/Building-extension#v1.5.1"
    },
    "files": [
        "README.md",
        "tutorial-01-chat.md",
        "tutorial-02-building.md",
        "tutorial-03-shapes.md",
        "tutorial-04-mobs.md"
    ],
    "public": true,
    "targetVersions": {
        "target": "1.7.25",
        "targetId": "minecraft"
    },
    "supportedTargets": [
        "minecraft"
    ],
    "preferredEditor": "blocksprj"
}
```

### pxt.json 필드 설명

| 필드 | 설명 | 예시 |
|------|------|------|
| `name` | 프로젝트 내부 이름 | `"basic-tutorials"` |
| `version` | 버전 번호 (Semantic Versioning) | `"1.0.0"` |
| `description` | 프로젝트 설명 | `"튜토리얼 모음"` |
| `dependencies` | 필요한 라이브러리/확장 | `{"core": "*", "builder": "*"}` |
| `files` | 프로젝트에 포함할 파일 목록 | `["tutorial.md"]` |
| `public` | 공개 여부 | `true` |
| `targetVersions` | 호환 버전 | `{"target": "1.7.25", "targetId": "minecraft"}` |
| `preferredEditor` | 기본 편집기 | `"blocksprj"` (블록) 또는 `"tsprj"` (코드) |

### 2.2 dependencies 설정

#### 기본 블록만 사용
```json
"dependencies": {
    "core": "*",        // MakeCode 핵심 (변수, 반복문 등)
    "builder": "*"      // Minecraft 블록 (blocks, player, mobs 등)
}
```

#### 외부 확장 추가
```json
"dependencies": {
    "core": "*",
    "builder": "*",
    "building": "github:사용자명/확장저장소명#v1.0.0"
}
```

**형식:**
- `"확장이름": "github:사용자명/저장소명#버전"`
- 버전은 Git 태그 (예: `v1.0.0`) 또는 브랜치 (예: `master`)

---

## 3. 튜토리얼 작성하기

### 3.1 Markdown 파일 생성

파일명: `tutorial-01-chat.md`

```markdown
# 채팅 기초 튜토리얼

## 소개 @unplugged

채팅 명령어를 사용하여 게임 내에서 코드를 실행하는 방법을 배워봅시다!

## 단계 1

``||player:on chat command||`` 블록을 작업 공간에 추가하세요.

```blocks
player.onChat("안녕", function () {

})
```

## 단계 2

``||player:say||`` 블록을 추가하여 메시지를 표시합니다.

```blocks
player.onChat("안녕", function () {
    player.say("안녕하세요!")
})
```

## 완료! @unplugged

축하합니다! 튜토리얼을 완료했습니다.
```

### 3.2 튜토리얼 Markdown 문법

#### @unplugged 지시어
```markdown
## 소개 @unplugged
```
- 코드 없이 설명만 표시하는 단계
- 소개, 중간 설명, 완료 메시지에 사용

#### 코드 블록
````markdown
```blocks
player.onChat("test", function () {
    player.say("Hello")
})
```
````
- MakeCode 블록 코드를 작성
- 자동으로 블록 형태로 변환됨

#### 블록 하이라이트
```markdown
``||player:on chat command||`` 블록을 추가하세요.
```
- `||카테고리:블록이름||` 형식
- 해당 블록을 왼쪽 도구상자에서 강조 표시

### 3.3 여러 튜토리얼 추가하기

1. 새 Markdown 파일 생성: `tutorial-02-building.md`
2. `pxt.json`의 `files` 배열에 추가:
```json
"files": [
    "tutorial-01-chat.md",
    "tutorial-02-building.md"  // 추가
]
```

---

## 4. GitHub에 업로드하기

### 4.1 Git 저장소 초기화

```bash
cd 프로젝트폴더
git init
git add .
git commit -m "Initial commit"
```

### 4.2 GitHub 저장소 생성

1. https://github.com/new 접속
2. Repository name: `makecodetutorial`
3. Public 선택
4. **Initialize 옵션 모두 체크 해제** (로컬에 이미 파일 있음)
5. Create repository 클릭

### 4.3 GitHub에 푸시

```bash
git remote add origin https://github.com/사용자명/makecodetutorial.git
git branch -M master
git push -u origin master
```

### 4.4 버전 태그 추가 (선택사항)

```bash
git tag v1.0.0
git push --tags
```

**버전 관리 팁:**
- 튜토리얼 수정할 때마다 버전 업데이트
- `pxt.json`의 `version` 필드도 함께 변경
- 태그를 사용하면 특정 버전 지정 가능

---

## 5. 튜토리얼 사용하기

### 5.1 URL 형식

**기본 형식:**
```
https://minecraft.makecode.com/#tutorial:github:사용자명/저장소명/파일명
```

**예시:**
```
https://minecraft.makecode.com/#tutorial:github:ssakspirit/makecodetutorial/tutorial-01-chat
```

**주의사항:**
- ✅ 확장자 **없이**: `/tutorial-01-chat`
- ❌ 확장자 포함: `/tutorial-01-chat.md` (작동 안 함)
- ❌ 서브폴더: `/tutorials/01-chat` (작동 안 함)

### 5.2 웹 브라우저에서 테스트

브라우저에서 URL 열기:
```
https://minecraft.makecode.com/#tutorial:github:ssakspirit/makecodetutorial/tutorial-01-chat
```

### 5.3 Minecraft에서 사용

#### 방법 1: 커맨드 블록
```
codebuilder navigate @p false https://minecraft.makecode.com/#tutorial:github:ssakspirit/makecodetutorial/tutorial-01-chat
```

#### 방법 2: education.json (자동 실행)

월드 폴더에 `education.json` 파일 생성:

**경로:**
- 설치 파일: `C:\Users\사용자명\AppData\Roaming\Minecraft Education Edition\games\com.mojang\minecraftWorlds\[월드폴더]\`
- 스토어: `C:\Users\username\AppData\Local\Packages\Microsoft.MinecraftEducationEdition_8wekyb3d8bbwe\LocalState\games\com.mojang\minecraftWorlds\[월드폴더]\`

**파일 내용:**
```json
{
    "codebuilder": {
        "canResize": true,
        "defaulturi": "https://minecraft.makecode.com/#tutorial:github:ssakspirit/makecodetutorial/tutorial-01-chat"
    },
    "commands": {
        "hiddenFromPlayer": [""]
    }
}
```

#### 방법 3: NPC
1. NPC 배치
2. 고급 설정 활성화
3. 명령어 입력:
```
codebuilder navigate @initiator false https://minecraft.makecode.com/#tutorial:github:ssakspirit/makecodetutorial/tutorial-01-chat
```

---

## 6. 문제 해결

### 6.1 "인터넷 연결 확인" 오류

**원인:**
- 튜토리얼 파일이 GitHub에 없음
- URL 형식이 잘못됨
- 파일명이 pxt.json의 files 배열에 없음

**해결:**
1. GitHub에서 파일 존재 확인:
   ```
   https://github.com/사용자명/저장소명/blob/master/tutorial-01-chat.md
   ```
2. pxt.json 확인:
   ```json
   "files": [
       "tutorial-01-chat.md"  // 파일명 정확한지 확인
   ]
   ```
3. URL에서 `.md` 확장자 제거

### 6.2 Building 블록이 안 보임

**원인:**
- dependencies에 확장이 없음
- 확장 버전이 잘못됨

**해결:**
```json
"dependencies": {
    "core": "*",
    "builder": "*",
    "building": "github:ssakspirit/Building-extension#v1.5.1"
}
```

### 6.3 튜토리얼 업데이트가 반영 안 됨

**원인:**
- MakeCode 캐시 (15-30분)

**해결:**
1. 버전 태그 변경:
   ```bash
   git tag v1.1.0
   git push --tags
   ```
2. URL에 버전 지정:
   ```
   #tutorial:github:사용자명/저장소명/파일명?v=1.1.0
   ```
3. 시크릿 모드로 브라우저 열기
4. 충분히 기다리기 (30분 이상)

### 6.4 서브폴더 튜토리얼이 안 됨

**문제:**
```
tutorials/01-chat/tutorial.md  ❌ 작동 안 함
```

**해결:**
모든 튜토리얼을 루트로 이동:
```
tutorial-01-chat.md  ✅ 작동
tutorial-02-building.md  ✅ 작동
```

---

## 7. 모범 사례

### 7.1 파일명 규칙
- 소문자 사용
- 하이픈으로 단어 구분
- 숫자 접두사로 순서 표시
- 예: `tutorial-01-chat.md`, `tutorial-02-building.md`

### 7.2 버전 관리
- Semantic Versioning 사용 (예: 1.2.3)
  - Major: 호환성 깨지는 변경
  - Minor: 새 기능 추가
  - Patch: 버그 수정

### 7.3 README 작성
- 튜토리얼 목록 명시
- 각 튜토리얼 URL 제공
- 사용 방법 설명

### 7.4 테스트
1. 로컬에서 먼저 작성
2. GitHub에 푸시
3. 웹 브라우저에서 테스트
4. Minecraft에서 최종 확인

---

## 8. 참고 자료

### 예제 프로젝트
- [Building-extension-tutorial](https://github.com/ssakspirit/Building-extension-tutorial) - 확장 사용 예제
- [makecodetutorial](https://github.com/ssakspirit/makecodetutorial) - 기본 블록 튜토리얼

### 공식 문서
- [MakeCode Extensions](https://makecode.com/extensions/getting-started)
- [GitHub Extension Authoring](https://makecode.com/extensions/github-authoring)

---

## 부록: 전체 작업 순서 요약

```bash
# 1. 프로젝트 폴더 생성
mkdir makecodetutorial
cd makecodetutorial

# 2. 파일 생성
# - pxt.json
# - tutorial-01-chat.md
# - tutorial-02-building.md
# - README.md

# 3. Git 초기화
git init
git add .
git commit -m "Initial commit"

# 4. GitHub 저장소 생성 (웹에서)

# 5. GitHub에 푸시
git remote add origin https://github.com/사용자명/makecodetutorial.git
git branch -M master
git push -u origin master

# 6. 태그 추가
git tag v1.0.0
git push --tags

# 7. 브라우저에서 테스트
# https://minecraft.makecode.com/#tutorial:github:사용자명/makecodetutorial/tutorial-01-chat

# 8. Minecraft에서 사용
# 커맨드 블록 또는 education.json 설정
```

---

**작성일:** 2025-12-06
**버전:** 1.0.0
**작성자:** 스티브코딩
