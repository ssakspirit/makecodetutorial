# 도형 그리기 튜토리얼

## 소개 @unplugged

Shapes 블록을 사용하여 멋진 도형을 그려봅시다!

## 단계 1

먼저 원을 그려봅시다.

``||shapes:circle||`` 블록을 사용하면 원을 그릴 수 있습니다.

```blocks
player.onChat("원", function () {
    shapes.circle(
        GOLD_BLOCK,
        player.position(),
        5,
        Axis.Y,
        ShapeOperation.Replace
    )
})
```

## 단계 2

이번에는 구(Sphere)를 만들어봅시다.

```blocks
player.onChat("구", function () {
    shapes.sphere(
        GLASS,
        player.position(),
        5,
        ShapeOperation.Replace
    )
})
```

## 단계 3

선을 그려봅시다.

``||shapes:line||`` 블록으로 두 점을 연결하는 선을 그릴 수 있습니다.

```blocks
player.onChat("선", function () {
    shapes.line(
        REDSTONE_BLOCK,
        pos(0, 0, 0),
        pos(10, 10, 10)
    )
})
```

## 단계 4

원의 외곽선만 그려봅시다.

ShapeOperation을 Outline으로 바꾸면 외곽선만 그립니다.

```blocks
player.onChat("링", function () {
    shapes.circle(
        DIAMOND_BLOCK,
        player.position(),
        8,
        Axis.Y,
        ShapeOperation.Outline
    )
})
```

## 단계 5

구의 외곽선으로 거대한 구조물을 만들어봅시다!

```blocks
player.onChat("돔", function () {
    shapes.sphere(
        QUARTZ_BLOCK,
        pos(0, 0, 0),
        15,
        ShapeOperation.Outline
    )
})
```

## 완료! @unplugged

축하합니다! 도형 그리기를 배웠습니다.

**시도해볼 것:**
- 다양한 크기의 원 그리기
- 여러 개의 구를 조합하여 눈사람 만들기
- Axis.X나 Axis.Z로 다른 방향의 원 그리기
- 무지개 색 원 여러 개 그리기
