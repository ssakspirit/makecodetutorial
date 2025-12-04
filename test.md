<!-- 코드작성기에 템플릿 코드를 작성할 수 있습니다. 코드작성기의 자바스크립트 코드로 작성된 것을 그대로 가져오면 됩니다. ```template ``` -->
```template
agent.teleportToPlayer()
player.onTravelled(WALK, function () {
})
```

<!-- 코드작성기에서 사용할 수 있는 명령블록들을 여기에 넣습니다. 자바스크립트의 코드를 가져옵니다. 이미 작성된 템플릿에 있는 명령블록들은 자동으로 들어갑니다. ```blocks ``` -->
```blocks
player.say(":)")
player.onTravelled(WALK, function () {})
player.onChat("run", function () {})

agent.teleportToPlayer()
agent.move(FORWARD, 1)
agent.turn(LEFT_TURN)
agent.place(FORWARD)
agent.destroy(FORWARD)
agent.collectAll()
if(agent.inspect(AgentInspection.Block, FORWARD) == 0)
if(agent.getPosition() == 0)
if(agent.detect(AgentDetection.Block, FORWARD) == 0)
agent.drop(FORWARD, 1, 1)

while (false) {}
if(true) {} else {}
for (let index = 0; index < 4; index++) {}

if(0 == 0)
if(randint(0, 10) == 0)
if(variable)

if(blocks.blockByName("stone") == 0)
if(blocks.blockById(0) == 0)
blocks.place(GRASS, pos(0, 0, 0))
if(GRASS == 0)
```
<!-- 제목입니다 -->
# My Tutorial 

<!-- #이 많아지면 제목 수준이 내려갑니다. ##제목으로 페이지를 구분합니다. -->
## Step 1
Step 1 instructions

## Step 2
Step 2 instructions

## Step 3
You accomplished your project, good job!



<!-- 각 스텝 아래 다음과 같이 힌트 코드를 넣을 수 있습니다. -->
```blocks
player.onChat("탐사", function () {
    agent.setAssist(DESTROY_OBSTACLES, true)
    agent.move(DOWN, 5)
    agent.move(FORWARD, 5)
    agent.move(DOWN, 2)
    agent.move(BACK, 3)
})
```