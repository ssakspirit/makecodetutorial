# 몹 생성 튜토리얼

## 소개 @unplugged

다양한 몹을 생성하는 방법을 배워봅시다!

## 단계 1

먼저 닭을 소환해봅시다.

``||mobs:spawn||`` 블록을 사용하면 몹을 생성할 수 있습니다.

```blocks
player.onChat("닭", function () {
    mobs.spawn(CHICKEN, player.position())
})
```

## 단계 2

이번에는 소를 소환해봅시다.

```blocks
player.onChat("소", function () {
    mobs.spawn(COW, player.position())
})
```

## 단계 3

여러 마리를 한번에 소환하려면 반복 블록을 사용합니다.

``||loops:repeat||`` 블록으로 5마리의 양을 소환해봅시다.

```blocks
player.onChat("양떼", function () {
    for (let index = 0; index < 5; index++) {
        mobs.spawn(SHEEP, player.position())
    }
})
```

## 단계 4

다양한 위치에 몹을 소환하려면 ``||positions:add||``를 사용합니다.

```blocks
player.onChat("동물원", function () {
    mobs.spawn(CHICKEN, positions.add(player.position(), pos(2, 0, 0)))
    mobs.spawn(COW, positions.add(player.position(), pos(-2, 0, 0)))
    mobs.spawn(SHEEP, positions.add(player.position(), pos(0, 0, 2)))
    mobs.spawn(PIG, positions.add(player.position(), pos(0, 0, -2)))
})
```

## 단계 5

늑대를 소환하고 울타리로 보호해봅시다!

```blocks
player.onChat("늑대", function () {
    mobs.spawn(WOLF, player.position())
    blocks.fill(
        FENCE,
        positions.add(player.position(), pos(-2, 0, -2)),
        positions.add(player.position(), pos(2, 1, 2)),
        FillOperation.Outline
    )
})
```

## 완료! @unplugged

축하합니다! 몹 생성 방법을 배웠습니다.

**시도해볼 것:**
- 다른 동물 소환하기 (HORSE, RABBIT, OCELOT)
- 원 모양으로 동물 배치하기
- 동물 농장 만들기
- 친구 몹과 적대 몹 구분하여 소환하기

**주의:** 적대 몹(ZOMBIE, SKELETON 등)은 조심해서 소환하세요!
