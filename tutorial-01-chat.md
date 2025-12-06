# 채팅 기초 튜토리얼

## 소개 @unplugged

채팅 명령어를 사용하여 게임 내에서 코드를 실행하는 방법을 배워봅시다!

## 단계 1

먼저 ``||player:on chat command||`` 블록을 작업 공간에 추가하세요.

"안녕"이라고 채팅하면 코드가 실행됩니다.

```blocks
player.onChat("안녕", function () {

})
```

## 단계 2

이제 ``||player:say||`` 블록을 추가하여 플레이어가 메시지를 말하도록 만들어봅시다.

```blocks
player.onChat("안녕", function () {
    player.say("안녕하세요!")
})
```

## 단계 3

여러 개의 채팅 명령어를 만들 수 있습니다.

"시간"이라고 채팅하면 현재 시간을 알려주는 명령어를 만들어봅시다.

```blocks
player.onChat("안녕", function () {
    player.say("안녕하세요!")
})
player.onChat("시간", function () {
    player.say("낮 시간입니다!")
})
```

## 단계 4

``||gameplay:time set||`` 블록을 사용하여 실제로 시간을 바꿔봅시다.

```blocks
player.onChat("낮", function () {
    gameplay.timeSet(DayTime.Day)
    player.say("낮으로 변경했습니다!")
})
player.onChat("밤", function () {
    gameplay.timeSet(DayTime.Night)
    player.say("밤으로 변경했습니다!")
})
```

## 완료! @unplugged

축하합니다! 채팅 명령어 사용법을 배웠습니다.

이제 다양한 명령어를 만들어보세요!

**시도해볼 것:**
- "비" 명령어로 날씨 바꾸기
- "점프" 명령어로 메시지 표시하기
- 자신만의 명령어 만들기
