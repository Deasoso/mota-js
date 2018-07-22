# HTML5 魔塔样板

## 简介

HTML5 canvas制作的魔塔样板，支持全平台游戏！
**即使完全不会编程的用户，按照模板和说明文档也能很快做出一个魔塔游戏！**

* [List / HTML5魔塔游戏列表](https://h5mota.com/)
* [Demo / 样板效果](https://ckcz123.com/games/template/)
* [Docs / 使用文档说明](https://ckcz123.github.io/mota-js/)
* [Video / 视频教程](http://www.bilibili.com/video/av17608025/)

![样板](./docs/img/sample0.png)

## 目录结构

``` bash
├── /_server/        # 为可视化地图编辑器提供一些支持的目录
├── /docs/           # 文档目录
├── /libs/           # 系统库目录
│ ├─ /thirdparty/    # 游戏所用到的第三方库文件
│ ├─ actions.js      # 处理用户交互的文件
│ ├─ core.js         # 系统核心文件（游戏入口，接口&转发）
│ ├─ control.js      # 游戏逻辑控制
│ ├─ data.js         # 记录了一些初始化信息
│ ├─ enemys.js       # 记录了怪物的信息，包括特殊属性、伤害计算公式、临界值计算等。
│ ├─ events.js       # 处理事件的文件，所有自定义事件都会在此文件中进行处理
│ ├─ icons.js        # 记录了图标信息
│ ├─ items.js        # 道具的使用
│ ├─ loader.js       # 动态加载JS代码、图片、音效等
│ ├─ maps.js         # 记录了地图信息，和地图绘制等操作
│ ├─ ui.js           # UI绘制信息，主要负责绘制各个UI窗口。
│ └─ utils.js        # 工具类
├── /project/        # 项目目录，用户需要在这里做自己的塔
│ ├─ /animates/      # 动画目录
│ ├─ /floors/        # 剧本文件，记录了每个地图的数据和事件
│ ├─ /images/        # 所有图片素材目录
│ ├─ /sounds/        # 音效目录
│ ├─ data.js         # 全局变量信息
│ ├─ enemys.js       # 怪物属性数据
│ ├─ functions.js    # 可能会被修改的脚本代码
│ ├─ icons.js        # 素材和ID的对应关系定义
│ ├─ items.js        # 道具的定义，获得道具的效果
│ └─ maps.js         # 地图和数字的对应关系
├── /常用工具/        # 一些常用工具，可以辅助造塔  
│ ├─ RM动画导出器.exe      # 能从RMXP中导出动画，以供H5使用。 http://github.com/ckcz123/animate_export/
│ ├─ JS代码压缩工具.exe    # 能对Javascript代码进行压缩和整合，从而减少IO请求量。 http://github.com/ckcz123/JSCompressor/
│ ├─ 便捷PS工具.exe        # 能只用复制和粘贴来快速对素材进行PS操作。  http://github.com/ckcz123/ps/
│ ├─ 地图生成器.exe        # 能从一张截图识别出来具体的数字数组，方便复刻已有的塔。 http://github.com/ckcz123/map_generator/
│ └─ 伤害和临界值计算器.exe       # 一个能帮助计算怪物的伤害和临界值的小工具。 http://github.com/ckcz123/magic-tower-calculator/
├── /启动服务(mac版).app/        # 启动服务的mac版本。  
├── editor.html      # 可视化地图编辑工具
├── editor-mobile.html      # 可视化地图编辑工具（手机版）
├── index.html       # 主程序，游戏的入口
├── main.js          # JS程序的入口，将动态对所需JS进行加载
├── style.css        # 游戏所需要用到的样式表
└── 启动服务.exe      # 一个本地的HTTP服务器，也能支撑前端的一些POST请求从而能拓展JS的IO功能。 http://github.com/ckcz123/mota-js-server/
```

## 更新说明

### 2018.7.21 V2.3.3

* [x] 将怪物特殊属性定义和伤害计算函数移动到脚本编辑中
* [x] 地图编辑器可以使用矩形方式绘制地图
* [x] 瞬间移动可以指定存在事件的点（如怪物、门、楼梯等）
* [x] 事件：画面震动
* [x] 事件：更新怪物数据
* [x] 移动事件和跳跃事件增加“不消失”选项
* [x] 修改默认bgm
* [x] 修复读档开启战斗动画等Bug
* [x] 大量细节优化

### 2018.7.9 V2.3.2

* [x] 适配手机端的造塔页面
* [x] 启动服务的多开版本
* [x] 新增事件：跟随效果
* [x] 怪物数据导出器
* [x] RM动画导出器也能导出音效
* [x] gif播放可随着分辨率自动放缩
* [x] 状态栏可随文字长度自动调整放缩
* [x] 楼传器一次可以翻10层
* [x] 也可以用status:exp来代替经验值的写法
* [x] V键也可以打开快捷商店
* [x] 破炸在周围只有一个目标时无需转向面对它
* [x] 道具效果中，无需再将null改成""才能双击编辑了
* [x] 各个已知Bug的修复，部分细节优化

### 2018.6.16 V2.3.1

* [x] 存档采用高比率压缩，单个大小是原来的1/10！
* [x] 默认存档数改成100页500个
* [x] base64上传成绩，杜绝乱码
* [x] 道具栏翻页
* [x] 单击瞬移（菜单栏中开关）
* [x] 重新补上E键打开光标
* [x] 楼层属性增添地下层选项，同层传送至上楼梯
* [x] core.debug()穿墙模式不能穿出地图
* [x] core.values和core.flags也存入存档
* [x] 修复所有已知bug

### 2018.5.27 V2.3

* [x] 启动服务和便捷PS工具（Mac版）
* [x] 地图编辑器可以右键复制或移动图块
* [x] 事件：while循环处理
* [x] 事件：等待用户操作并获得按键或点击信息
* [x] 地图数据统计
* [x] 衰弱可以减少攻防的比例
* [x] 便捷PS工具可以批量导入素材
* [x] 楼层转换可以直接指定“上一楼”和“下一楼”
* [x] 地图编辑器可以使用滚轮切换楼层
* [x] 除Autotile外均可自动注册
* [x] 支持status:x获得当前坐标
* [x] core.debug()改成调试模式，可以Ctrl穿墙
* [x] 新建地图可以保留楼层属性
* [x] 地图编辑器可用PageUp和PageDown切换楼层
* [x] 提供大量素材，可直接取用
* [x] 重写大部分教程，新增大量拓展描述
* [x] 大量细节进行优化，所有已知的bug进行了修复

### 2018.5.6 V2.2

* [x] 事件坐标可用变量指定("loc": ["flag:x", "flag:y"])
* [x] 全局商店也可以使用图块编辑
* [x] 高亮显示有事件的格子
* [x] 对于道具和怪物自动注册该列所有未注册的素材
* [x] 便捷PS工具对于白底图片可自动调整为透明背景
* [x] 事件：等待用户点击(type:wait)
* [x] 事件：图片移动事件(type:moveImage)
* [x] 事件：设置BGM音量(type:setVolume)
* [x] 提供core.rand()和core.rand2()两个随机数函数
* [x] 作弊处理（最大有效生命值、匿名则最低成绩上传）
* [x] 自定义状态栏绘制
* [x] 最高六倍速播放
* [x] 播放录像时可以C键查看怪物手册
* [x] 修复标题文字太长导致无法开始游戏的问题
* [x] 新增纯新手简易造塔流程
* [x] 部分效果和性能的优化

### 2018.4.25 V2.1.1

* [x] 新增事件：改变勇士行走图
* [x] 楼传器落点设置
* [x] 录像回放从任意存档点开始
* [x] 录像过程中允许存档
* [x] 血网显伤
* [x] 怪物手册显示接下来的临界表
* [x] 重置当前楼层地图core.resetMap()
* [x] 支持部分楼层不允许浏览地图
* [x] 修复部分浏览器无法进入游戏的Bug
* [x] 其他细节优化

### 2018.4.19 V2.1

* [x] 编辑器添加新建和删除按钮；地图自动保存
* [x] 录像支持倒退（录像播放中每20步存一个节点，最多30个）
* [x] Gif支持：可以作为楼层背景图或者使用显示动图事件
* [x] 图片显示增加淡入淡出效果
* [x] APP端也能下载或读取文件
* [x] 地图临界显伤
* [x] 单个存档清理
* [x] 大数据魔塔的支持
* [x] 进一步对JS文件和图标进行压缩，大幅提高加载速度
* [x] 修复有时候无法输入ID的问题
* [x] 其他细节优化

### 2018.3.17 V2.0.1

* [x] 道具使用效果的进一步分离
* [x] 支持插件编写，用户可以根据需求来写插件了
* [x] 文本编辑器支持自动补全和代码纠错
* [x] 部分UI界面发生变化，更加方便和美观
* [x] 所有已知Bug的修复

### 2018.3.14 V2.0

* [x] 全GUI造塔，现在用户无需打开任何文件直接编辑JS代码了。
* [x] 整体改变目录架构，将数据和逻辑进行分离
* [x] 支持48x32的怪物和NPC素材
* [x] 加点改成系统开关进行处理，怪物手册会列出加点值
* [x] 支持带有血量上限的塔
* [x] 增加前景图片绘制
* [x] 便捷PS工具对于非标准的图片可以自动进行调整
* [x] 录像存储机制进行修改，对于道具记录全ID
* [x] 其他细节的优化

### 2018.2.9 V1.4.1

* [x] 改变图块（setBlock事件）。
* [x] 同一个点的多事件处理（做法详见文档）。
* [x] 增加新地图后可以接档而不用重新开始。
* [x] 增加可以接收用户输入的事件(type:input)。
* [x] 滚动字幕；自动剧情文本。
* [x] 可以同时show/hide多个事件。
* [x] 现在可以支持滑冰和推箱子事件了。
* [x] 地图中每个块的可通行方向控制（悬崖效果）。
* [x] 动画支持带旋转和翻转的帧。
* [x] 长按屏幕可跳过对话。
* [x] 现在可以允许用户丢弃道具了（例如不会再使用的装备）。
* [x] 修复行走时按键会发生动画抖动问题。
* [x] 修复无法打开战斗动画的Bug。

### 2018.2.6 V1.4

* [x] 支持动画。
* [x] 瞬间移动。
* [x] 支持天气系统，可以在剧本中设置默认天气。
* [x] 新增自定义事件-图片显示。
* [x] 同时可以在剧本中设定多个背景素材。
* [x] 剧情文本特性控制，人物的对话框效果。
* [x] 单存档同步到服务器，下载到文件和读取。
* [x] 键盘支持自动寻路操作。
* [x] 浏览地图模式下可以查看怪物数据。
* [x] 未成功打怪和开门则不自动存档。
* [x] 重新支持楼梯穿透。
* [x] 支持多结局，成绩将分开统计。
* [x] 重构全局动画、行走动画和行走检测，大幅提升性能。
* [x] 修复所有已知Bug。

### 2018.1.21 V1.3.2

* [x] 增加录像和回放功能。
* [x] 增加统计功能，现在能看到每部塔的游戏人数、通关人数和当前MAX了。
* [x] 增加浏览地图功能，玩家可以快速查看每层楼的地图。
* [x] 现在保存文件到本地，以及从本地文件读档了。
* [x] 可以在全局开关中设置剑盾是否作为装备存在。
* [x] 修复了部分已知Bug。

### 2018.1.12 V1.3.1

* [x] 增加虚拟键盘
* [x] 增加自动存档（回退），A键可快速读档
* [x] 修复几处较为严重的Bug

### 2018.1.1 V1.3

* [x] 支持全键盘操作。
* [x] 支持将某个图片作为某层的背景素材。
* [x] 便捷PS工具支持更改图片色相。
* [x] 支持经验升级（进阶/境界塔）。
* [x] 打败怪物可以进行加点（加点塔）。
* [x] 增加阻击、N连击等属性；在怪物手册有属性显示。
* [x] 支持九宫格领域和大范围领域。
* [x] 增加负伤。
* [x] 支持各种BGM的播放。
* [x] 支持不同层使用不同的地面素材；支持多个Autotile同时存在。
* [x] 许多细节进行了优化，一些已知的Bug进行了修复。

### 2017.12.21 V1.2

* [x] 新增：本地HTTP服务器。
* [x] 新增：可视化地图编辑工具。
* [x] 新增：便捷PS工具。
* [x] 移除了meaning.txt，现在“地图生成器”将直接从js文件中读取数字和图块对应关系。
* [x] 新增：对Autotile图块的支持。
* [x] 新增：怪物支持多种属性；添加仇恨属性。
* [x] 移除了不再支持的checkBlock，现在对于领域和夹击无需再手动指定可能的点了。
* [x] 新增：单向箭头、感叹号（单次通行）的支持。
* [x] 新增：更多的默认素材，现在对于大多数地图风格无需P图，直接替换即可。
* [x] 添加部分自定义事件，部分细节优化，一些已知的Bug进行了修复。

### 2017.12.16 V1.1

* [x] 新增：战斗过程显示，可以在设置中关闭
* [x] 新增：勇士支持48*32（大图）的行走图
* [x] 新增：更改画面色调
* [x] 新增：文字显示支持自动换行
* [x] 部分修改状态栏UI
* [x] 增添Web的Markdown文档，移除原本的doc和pdf文档。
* [x] 修复若干Bug。

### 2017.12.9 V1.0

* [x] 发布初版HTML5魔塔样板

## 联系我们

本塔由 [`ckcz123`](https://github.com/ckcz123) （百度ID `艾之葵`）编写。

HTML5魔塔交流群群号： `539113091`

如有其它意见或建议，也可以通过发[issues](https://github.com/ckcz123/mota-js/issues)、或邮件至[ckcz123@126.com](mailto:ckcz123@126.com)联系我。
