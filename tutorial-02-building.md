# Building Extension으로 건축하기

## 소개 @unplugged

Building Extension을 사용하면 복잡한 건물을 쉽게 만들 수 있습니다!

기본 블록으로 만들기 힘든 건물들을 간단하게 만들어봅시다.

## 단계 1

먼저 "1"이라고 채팅하면 작은 집을 만들어봅시다.

``||player:on chat command||`` 블록을 추가하세요.

```blocks
player.onChat("1", function () {

})
```

## 단계 2

``||building:직각 건물 속성 정하기||`` 블록으로 건물의 크기와 재료를 설정합니다.

```blocks
player.onChat("1", function () {
    building.직각건물속성정하기(
        10,
        10,
        8,
        4,
        0,
        COBBLESTONE,
        PLANKS_OAK,
        LOG_OAK,
        PLANKS_OAK,
        BRICK_BLOCK,
        1,
        true,
        GLASS,
        2,
        2
    )
})
```

## 단계 3

``||building:ㅁ형 건물 생성||`` 블록으로 건물을 만듭니다!

```blocks
player.onChat("1", function () {
    building.직각건물속성정하기(
        10,
        10,
        8,
        4,
        0,
        COBBLESTONE,
        PLANKS_OAK,
        LOG_OAK,
        PLANKS_OAK,
        BRICK_BLOCK,
        1,
        true,
        GLASS,
        2,
        2
    )
    building.ㅁ형건물생성()
})
```

## 단계 4

이제 "2"라고 채팅하면 더 큰 건물을 만들어봅시다!

```blocks
player.onChat("2", function () {
    building.직각건물속성정하기(
        20,
        15,
        15,
        5,
        0,
        STONE,
        QUARTZ_BLOCK,
        STONE_BRICKS,
        WHITE_CONCRETE,
        RED_CONCRETE,
        2,
        true,
        GLASS,
        3,
        2
    )
    building.ㅁ형건물생성()
})
```

## 단계 5

원형 건물도 만들 수 있습니다!

"3"이라고 채팅하면 원형 타워를 만들어봅시다.

```blocks
player.onChat("3", function () {
    building.원형건물속성정하기(
        8,
        12,
        4,
        0,
        COBBLESTONE,
        PLANKS_OAK,
        STONE_BRICKS,
        LIGHT_GRAY_CONCRETE,
        1
    )
    building.원형건물생성()
})
```

## 완료! @unplugged

축하합니다! Building Extension으로 건물 만들기를 배웠습니다!

**시도해볼 것:**
- ㄱ형, ㄷ형 건물 만들기
- 지붕 형태 바꾸기 (삼각형, 피라미드, 돔)
- 다른 재료 사용하기
- 크기 조절하기
