# recipe++——超可口的香草风味配方包

## 前言

recipe++（简称rpp）添加了大量原版生存向配方，主要参照1.19+版本编写，在过程中注意了向下兼容性，适用于1.17+的所有版本。

### 为什么只向下兼容到1.17？

有一个致命的原因：

- 1.14重整了染料，因此1.14+版本的染料id与1.13.2-不同，1.14+的染色配方无法在1.13.2-正常使用；

还有一个影响美观（但不影响使用）的问题：

- 由于[MC-258762](https://bugs.mojang.com/browse/MC-258762)，1.17引入的粗矿切制配方在1.16.5-会无法避免地变为空白配方。

另外三个麻烦（但能解决）的问题：

- 1.13.2-的配方"type"值不能以"minecraft:"开头，否则游戏无法识别，其他文件未发现此现象；
- 1.16.2为标签文件引入了"request"选项，但包含了"request"的标签文件无法被1.16.1-识别，引用了这些标签的文件不会按照预期运行，需要分离为两个文件；
- 1.17扩充了物品谓词，旧的结构不会被读取，把新旧两个版本都写上就可以做到跨版本使用。

目前发布版本仅兼容1.17+，由于历史原因，版本号从v4开始；目前数据包正在逐步向下兼容，最终的目标是兼容到1.14，敬请期待rpp的未来版本。

### rpp的优势在哪里？

- 内容众多但不失原版风味，——我参考很多前人发布的配方列表，并尽可能多地在这一个包中添加了大量的配方；
- 完善的进度系统来获取配方，——一个完整的配方包必须完备，即使使用者没有阅读这份说明，他们也能在这套系统下逐渐发掘这个包的所有可能；
- 合理的分类整理，——"group""category"合理运用，整个配方书井井有条，优雅舒适！
	- 此功能需要在1.19.3+才能完整体验。
- 清晰的文件分类，——对照说明文档，您可以轻松地找到对应配方的位置，进度文件的路径与对应配方完全相同，便于您进行二次修改。

### 特别提醒：

- 本数据包修改了大量原版配方，大部分都是仅进行分类，我无法保证rpp与其他配方包的兼容性，但是大部分后果应该只是分类被破坏而已；
- rpp在[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)下共享，您可以在遵守规则的情况下自由地使用这份作品。

不过说实话，这个数据包的技术含量并没有多少，基本上算个纯体力活。我尽可能地把它做到优雅，给其他人做好结实的轮子，希望它能给你带来一个舒服的体验~

以下是内容说明——

## 通用的规则

1. 涉及多个同类物品的配方，不同物品允许混搭。
2. 未提及解锁条件和分类位置的配方，与原版相同产物配方相同。
3. 无特殊说明，产物相同或同类的配方共用配方书的同一格。
4. 配方产物、冶炼时间与原料投入呈正比。
5. 未说明配方类型，默认为合成配方。

### 修改（\\minecraft）

修改的原版配方。

1. 蜡烛、玻璃、玻璃板和陶瓦可以重复染色；

	相应的配方可以由对应染料解锁。
	- “玻璃板合成”和“玻璃板染色”在配方书中被拆开了。

2. 床、地毯、羊毛染色配方移植至1.19.4-。
	- 床、地毯的染色配方移入“杂项”分类。

3. 玻璃瓶、信标、末地水晶、阳光传感器和遮光玻璃可以由染色玻璃合成；

	玻璃瓶的配方可以由染色玻璃解锁。

4. 活塞、侦测器、投掷器、发射器和拉杆可以由黑石或深板岩原石合成；

	拉杆的配方可以由黑石或深板岩原石解锁。

5. 比较器、中继器和切石机也可以由深板岩合成。
6. 砂土可以由草方块、灰化土、菌丝、土径、耕地或缠根泥土合成。
7. 潜影盒、曲奇、面包和纸可以无序合成。
8. 盾牌可以作为燃料，烧冶1个物品。
9. 兔肉煲的两个配方合二为一。
10. 旗帜图案、石头压力板和磨制黑石压力板、石头按钮和磨制黑石按钮、竹栅栏和木制栅栏、竹栅栏门和木制栅栏门分别被整合进了配方书的同一格。
11. 带釉陶瓦的烧冶配方、盔甲纹饰锻造模板合成配方被整合进了配方书的同一格。
12. “树皮木合成”和“去皮木合成”在配方书中被拆开了。
13. 部分配方书被打上了组别，使其能够与新加入的同类配方共用配方书的同一格。
14. 收纳袋的配方移植至1.19.2-。
15. 末影龙死亡后会掉落龙首。
16. 蜜脾块、竹马赛克移入“建筑”分类，

	马铠、船类和乘骑钓竿移入“装备”分类，

	铁轨类、矿车类、唱片机和紫水晶块移入“红石”分类。

	红石矿冶炼移入“杂项”分类。
17. 启用了4种原版未使用的画。
	- 仅1.19+

### 染色（\\dye）

与物品染色相关的配方。

1. 混凝土粉末、混凝土和带釉陶瓦可以染色；

	获得任意相应物品时解锁配方。
	- “混凝土粉末染色”与原版的“混凝土粉末合成”在配方书中各自独立占位。

2. 已染色的蜡烛、玻璃、玻璃板和陶瓦可以用水桶褪色；

	在任意炼药锅中填充水时解锁配方。

### 缩合（\\condensation）

压缩为主题的配方。

#### 简化（\\simplification ）

减少合成过程中背包占用的配方。

1. 箱子、碗、物品展示框、画、音符盒和唱片机可以由原木类方块或竹块合成。
2. 木棍可以由2块原木类方块或竹块合成；

	获得原木类方块或竹块时解锁配方。

3. 梯子可以由木板、原木类方块或竹块合成；

	获得木板、原木类方块或竹块时解锁对应配方。

4. 骨块可以由9个骨头合成；

	获得骨头时解锁配方。

5. 锁链可以由2个铁锭和1个铁块合成；

	获得铁锭或铁块时解锁配方。

6. 各种粗矿物块可以在高炉中烧冶成相应的矿物块；

	获得对应粗矿物块时解锁配方；

	位于方块类。

7. 各种矿车可以在矿车的配方中心添加对应内容物合成；

	获得对应内容物时解锁配方。

8. 运输船可以在船的配方中心添加箱子合成；

	获得箱子时解锁配方。
	 - 与原版的无序合成在配方书中各自独立占位。

#### 转化（\\conversion）

为一些物品提供了新用途的配方。

1. 黏性活塞可以用水桶洗去黏性；

	获得黏性活塞时解锁配方。

2. 发射器可以由1个投掷器和1个弓合成，也可以在弓的配方中心添加投掷器合成；

	获得投掷器时解锁配方，前者也可以在获得弓时解锁。

3. 钓鱼竿可以由1个胡萝卜钓竿或诡异菌钓竿合成；

	获得胡萝卜钓竿或诡异菌钓竿时解锁配方。

4. 光灵箭可以由1个箭和1个萤石合成；

	获得萤石时解锁配方。

5. 遮光玻璃可以由1个玻璃和1个紫水晶块合成；

	获得紫水晶块时解锁配方。

6. 闪长岩和花岗岩可以由石英块合成；

	获得石英块时解锁配方。

7. 海晶石砖和暗海晶石可以由海晶石合成；

	获得海晶石时解锁配方。

8. 红色下界砖块可以由1个下界砖块和4个下界疣合成。
9. 火把与灵魂火把、灯笼与灵魂灯笼、营火与灵魂营火可以互相转化，

	获得对应被转化物品时解锁配方。

10. 蜂箱可以由3个蜜脾块和6个原木类方块合成；

	获得蜜脾块时解锁配方。

11. 蜘蛛网可以分解为9个线；

	获得蜘蛛网时解锁配方；

	位于杂项类。

12. 蜜脾块可以分解为4个蜜脾；

	获得蜜脾块时解锁配方；

	位于杂项类。

13. 竹块可以切制为9个竹子。
14. 脚手架可以由6个竹块和1个蜘蛛网合成；

	获得竹块时解锁配方。

#### 代价（\\cost）

简化但消耗更高的配方。
1. 金苹果、金胡萝卜和闪烁的西瓜片可以由金块或金锭合成；

	获得金块或金锭时解锁配方。

2. 灯笼和灵魂灯笼可以由铁锭合成。

3. 红色下界砖块可以由3个下界疣块和6个下界砖块合成；

	获得下界疣块时解锁配方。

4. 标靶可以由3个红石块和6个干草块合成；

	获得红石块时解锁配方。

5. 红石灯可以由3个红石块和6个萤石合成。

### 再生（\\renewability）：

再生部分不可再生资源的配方。

1. 龙首可以由1个龙蛋和8个龙息合成；

	杀死末影龙时解锁配方；

	位于装备类。

2. 树苗可以在篝火上烘烤为枯死的灌木；

	获得任意树苗时解锁配方；

	位于杂项类。

3. 方解石可以由1个滴水石块和1个骨块合成；

	获得滴水石块时解锁配方；

	位于建筑类。

4. 凝灰岩可以由1个岩浆块和1个沙砾合成；

	获得岩浆块时解锁配方；

	位于建筑类。

5. 深板岩可以由1个凝灰岩和1个砂岩或红砂岩合成；

	获得凝灰岩时解锁配方；

	位于建筑类。

6. 镶金黑石可以由1个黑石和4个金粒合成；

	获得镶金黑石时解锁配方；

	位于建筑类。

7. 蜘蛛网可以由9个线合成。

	获得蜘蛛网时解锁配方；

	位于杂项类。

8. 附魔金苹果可以由1个金苹果和8个金块合成。

	获得附魔金苹果时解锁配方；

	位于杂项类。

9. 铁、金或钻石马铠可以由7个铁锭、金锭或钻石合成。

	获得对应原料时解锁配方；

	位于装备类。

10. 鞘翅可以由1个龙首、1个末地水晶、1个紫颂花、2个潜影壳和4个幻翼膜合成。

	获得鞘翅时解锁配方；

	位于装备类。

11. 海绵可以由1个热带鱼、4个海晶碎片和4个海晶沙砾合成。

	获得海绵时解锁配方；

	位于装备类。

12. 海洋之心可以由1个干海带块、1个珊瑚块、1个蓝冰、1个岩浆块、1个海晶灯、1个湿海绵、1个三叉戟、1个海龟壳和1个河豚桶合成。

	获得海洋之心时解锁配方；

	位于杂项类。

13. 猪鼻盾徽可以由1个纸和1个猪灵的头合成；

	获得猪灵的头时解锁配方；

	位于杂项类。

### 切制（\\cutting ）

切石机配方；获得原料时解锁配方。

1. 下界砖块可以切制为2个下界砖栅栏。
2. 雪块可以切制为2个雪。

#### 锯木（\\woodcutting ）

仿照石头配方切割木头，部分配方原料利用率有所提升。

1. 木板类方块可以切制为相应的台阶或楼梯。
2. 原木类方块和竹块可以切制为相应的去皮版本。
3. 原木类方块和竹块可以切制为相应的台阶、楼梯、栅栏或栅栏门。

#### 分解（\\cut_down ）

拆解为合成原料的配方。

1. 末影箱可以切制为8个黑曜石。
2. 黏土块可以切制为4个黏土球。
3. 萤石可以切制为4个萤石粉。
4. 西瓜可以切制为9个西瓜片。
5. 海晶灯可以切制为5个海晶沙砾。
6. 镶金黑石可以切制为4个金粒。
7. 矿物锭或矿物块可以切制为相应的粗矿物或粗矿物块。
8. 下界合金锭可以切制为4个下界合金碎片。

### 灵感（\\inspiration ）

有趣但不失平衡的配方。

1. 损坏的铁砧可以在锻造台中用1个铁块修复到上一损坏阶段；

	获得相应程度的损坏的铁砧时解锁配方。
	- 仅1.19.3-

2. 石化橡木台阶可以在锻造台中用其他任意硬度为2的台阶强化橡木台阶获得；

	获得橡木台阶时解锁配方。
	- 仅1.19.3-

3. 附魔之瓶可以由1个任意喷溅型药水和8个幽匿块合成；

	获得幽匿块时解锁配方；

	位于装备类。

彩蛋：玩家被手持剑、斧或三叉戟的玩家直接杀死时会掉落头颅。

## 特别鸣谢

[Minecraft Wiki](https://minecraft.fandom.com/zh/wiki/Minecraft_Wiki)团队：他们整理的详实资料为了提供了无比强大的帮助；

[创小业](https://space.bilibili.com/133430292)：他的[数据包系列教程](https://www.bilibili.com/video/BV1jS4y1j77W)将我引入数据包制作的大门；

[SunnySlopes](https://space.bilibili.com/100377977)：[cv11805605](https://www.bilibili.com/read/cv11805605)点燃了我的创作动力，启发了下界合金锭分解、枯木再生、粗矿切制、龙头合成、物品褪色、发射器合成、无序合成等配方；

[XeKr](https://space.bilibili.com/5930630)：[cv12992062](https://www.bilibili.com/read/cv12992062)，启发了原木合箱子、铁锭合矿车、切石机分解、活塞去黏性、附魔金苹果等配方；

[Molforte](https://space.bilibili.com/353561345)：[cv9789415](https://www.bilibili.com/read/cv9789415)，启发了铁砧修复配方；

[唐沢咲川NaN](https://space.bilibili.com/417883773)：[cv16388612](https://www.bilibili.com/read/cv16388612)，启发了石化橡木台阶配方；

以及阅读并使用这份数据包的你。
