# 건축 기초 튜토리얼

## 소개 @unplugged

블록을 배치하고 건물을 만드는 방법을 배워봅시다!

## 단계 1

``||player:on chat command||`` 블록으로 시작합니다.

"블록"이라고 채팅하면 블록을 배치해봅시다.

```blocks
player.onChat("블록", function () {

})
```

## 단계 2

``||blocks:place||`` 블록을 사용하여 플레이어 위치에 블록을 배치합니다.

```blocks
player.onChat("블록", function () {
    blocks.place(GOLD_BLOCK, player.position())
})
```

## 단계 3

이제 작은 벽을 만들어봅시다.

``||blocks:fill||`` 블록을 사용하면 여러 블록을 한번에 배치할 수 있습니다.

```blocks
player.onChat("벽", function () {
    blocks.fill(
        PLANKS_OAK,
        pos(0, 0, 0),
        pos(5, 3, 0),
        FillOperation.Replace
    )
})
```

## 단계 4

이제 간단한 집을 만들어봅시다!

``||blocks:fill||``의 Outline 모드를 사용하면 외곽선만 그릴 수 있습니다.

```blocks
player.onChat("집", function () {
    blocks.fill(
        PLANKS_OAK,
        pos(0, 0, 0),
        pos(5, 3, 5),
        FillOperation.Outline
    )
    blocks.fill(
        COBBLESTONE,
        pos(0, 0, 0),
        pos(5, 0, 5),
        FillOperation.Replace
    )
})
```

## 단계 5

지붕도 추가해봅시다!

```blocks
player.onChat("집", function () {
    blocks.fill(
        PLANKS_OAK,
        pos(0, 0, 0),
        pos(5, 3, 5),
        FillOperation.Outline
    )
    blocks.fill(
        COBBLESTONE,
        pos(0, 0, 0),
        pos(5, 0, 5),
        FillOperation.Replace
    )
    blocks.fill(
        BRICK_BLOCK,
        pos(0, 4, 0),
        pos(5, 4, 5),
        FillOperation.Replace
    )
})
```

## 완료! @unplugged

축하합니다! 기본 건축 방법을 배웠습니다.

**시도해볼 것:**
- 더 큰 집 만들기
- 다른 재료 사용하기 (STONE, BRICK_BLOCK, GLASS)
- 창문 추가하기
- 여러 층 건물 만들기
