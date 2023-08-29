# 中文键盘输入

### 概述

#### 历史沿革

* 创造历史：前打字时代
  * 写作术
    * 介质：龟甲、竹简、石碑、钟鼎
    * 工具：刻刀、毛笔
  * 造纸术
  * 印刷术
* 历尽艰辛：打字机时代。说起中文键盘输入，中国人有着上百年的痛苦经历，为此在技术发明和文字改革两条路上进行了长期、艰苦的探索，牵动着每一个中国人的神经，直到个人计算机的普及，才给围绕汉字存亡的激烈争斗划上了句号。
  * 机械打字
    * 轻便的英文打字机，迅速普及，打字快速，成本低廉
    * 笨重的中文打字机，无法普及，打字缓慢，成本高昂
      * 舒式打字机：列举法
      * 明快打字机：编码法
  * 铅字印刷
  * 电报电传
  * 写作工具：钢笔、铅笔、圆珠笔
* 涅槃重生：输入法时代。计算机的出现拯救了汉字，彻底终结了中文键盘输入的百年困境。
  * 电子打字机
    * 七十年代：港台
    * 八十年代：大陆，四通打字机
  * 激光照排术
  * 中文输入法
    * 七十年代：繁体输入法兴起，仓颉、注音、支秉歧的见字识码
    * 八十年代：简体输入法攻关，简拼、首尾、快速、五笔、双拼双音、自然码。第一代盛行，第二代开始和发展。
    * 九十年代：智能狂拼（自通输入法、黑马神拼、拼音之星），智能ABC，微软拼音，二笔，T9拼音和笔画、文字码（字母选重）。第二代盛行和第三代开始。
    * 零零年代：紫光拼音，拼音佳佳，搜狗拼音，网络词库，声笔码（顶功出现）。第三代盛行，第四代开始。
  * 手机输入法时代
    * 一零年代：百度，QQ输入法，手心输入法，必应拼音，谷歌拼音，声笔简码（顶功发展）。第四代发展，第五代开始。
    * 二零年代：讯飞，华为小艺，微信键盘，章鱼、触宝，声笔Rime（顶功成熟）。第四代盛行，第五代发展。
* 不容乐观：存在的问题
  * 重解码，轻编码
  * 重易学、轻效率：一切为了拉新、留存、促活和转化（广告、捆绑、弹窗）
  * 同质化：跟风、无创新、仅仅愿意利用现有流行技术来做商业化
  * 免费与回报：羊毛出在羊身上还是羊毛出在猪身上？
  * 恶性循环：用户和供方双输
* 未来可期：解决的方法。
  * 顶功编码：解决强关联输入问题
  * 人工智能：解决弱关联输入问题
  * 良性循环：如何建立良性循环？

#### 基本概念

* 中文键盘输入的定义：用户将中文通过键盘输入到智能设备中
* 中文与汉字
* 内码与外码：交换码与输入码
* 音码、形码、音形码、形音码
* 重码率
* 码长、码元、码位
* 特征（信息）
* 编码单位、解码单位：编码和解码的单位在字词型输入方案中是一致的，而在整句型方案中一般是不一致的。后者的编码单位是字，而解码单位可以是字、词或句。解码单位对应的是上屏单位。
* 整句模式、字词模式
* 熵（每字符的信息量）、熵率（每秒钟的信息量）、冗余度（1-信息率）、信息率（相对率，无穷熵÷零阶熵）

### 理论

#### 输入模型

* 历史模型
  * 集合模型
  * 过程模型
  * 认知模型
  * _通信模型：有利于采用信息论作为理论基础，提供极限值和努力方向；有利于借鉴和参考通信的成功实践。但是，需要结合中文的特殊性和重视人的因素。_
  * HHM模型
  * LSTM模型
  * Transformer模型
* 建议模型：信息论模型，通信模型，中文键盘输入系统
  * 要点
    * 香农三大定理：X可达但不可超。可达讲的是充分条件，不可超讲的是必要条件。定理1是定理3的特例。三大定理均用AEP性质来证明，大数定律在证明中发挥了决定性作用。
      1. 信源压缩定理：X=压缩率
      2. 信道容量定理：X=传输率
      3. 信源保真定理：X=保真度
    * 中文信源的熵与熵率
      * 中文总体只是一个基础信源
      * 用户的中文与总体有偏离，可看成是从总体衍生出的个体信源
      * 用户的不同使用场景可能还会有进一步的偏离，可看成是从用户信源衍生出的场景信源
    * 中文信道的容量，要考虑正反两个方向
      * 无反馈模型
      * 有反馈模型
    * 看打、听打和想打三种不同场景的分析
      * 信源速率
        * 可控：看打和想打一般是可控的，但是游走字幕是不可控的
        * 不可控：听打一般是不可控的，但是录音回放是可控的
      * 信道噪声
        * 看打抗噪能力强
        * 听打和想打抗噪能力弱
  * 人
    * 大脑：信源、发送器（编码器）
    * 手指：信道（正向）
    * 眼睛：信道（反向）
  * 机（工具，纸墨笔砚）
    * 主机（电脑，手机，平板等）：信宿、接收器（解码器）
    * 键盘（机械键盘，触摸键盘）：信道（正向）
    * 屏幕（显示器，触屏）：信道（反向）

#### 过程分析

在建议模型的基础上，来进行过程分析。输入速度 = 输入字数 ÷ 输入时间。输入时间 = 编码时间 + 击键时间 + 交互时间 +处理时间。字词模式：字词→编码→字词选项→选择，编码单位和解码单位一致，均为单字或者词组（包括复合词组甚至非词组合）。整句模式：单字→编码键→字词句选项→选择，编码单位是单字，编码可以是全码或者简码，截止长度由用户决定，可以是单字、词组、短语或者句子。解码方式由输入法决定，分解单位可以是单字、词组、短语或者句子。两种模式在解码时都可以考虑或者不考虑将历史输入作为限制，即可以是无状态的或者有状态的。 现成的分析素材是人们的打字录屏，主要来自于B站。将打字录屏下载后，加以分类，用PR加载后进行慢放、快放和逐帧分析都可以。将打字的时间消耗归集到每一个编码和解码单位。

* 编码时间
  * 获取时间
    1. 想打（含默打）
    2. 看打
    3. 听打
  * 切分时间
  * 编码时间
    1. 逐键与批量：逐键有利于及时纠错，批量有利于提高键速
    2. 静态与动态：静态有利于条件反射，动态有利于缩短码长
    3. 定长与变长：定长有利于降低难度，变长有利于缩短码长
* 击键时间
  * 查看时间：不能触打而需要观察按键时就需要查看时间
  * 定位时间：取决于键集大小和按键布局，以及动作能力
  * 击打时间：取决于按键灵敏度和动作能力
* 交互时间：用眼睛和耳朵获取反馈信息而消耗的时间，但不含看打和听打时获取消息的时间。
  * 选择时间
    1. 查看时间
    2. 定位时间
    3. 翻页时间
  * 质保时间
    1. 确认时间
    2. 查错时间
    3. 纠错时间
* 处理时间：指设备的处理时间，一般情况下都非常短可以忽略，很少有导致用户等待的情况。但是，在网络延迟大的时候，访问云词库可能会感觉到有明显的等待过程。

#### 评价标准

在过程分析的基础上来确定评价指标。

* 简单性（经济性）
  * 易学性：背景知识，学习期
    * 国民教育背景：我国现行中小学教材中已包含了下述四个方面的内容
      1. 认识3000左右汉字；
      2. 掌握汉语拼音方法拼写汉语的字、词；
      3. 会使用部首检字法查字典；
      4. 按正确笔顺书写汉字。
    * 其它背景知识
      * 已经学会的中文输入方案，如拼音和五笔等：可能有正反两方面的作用
      * 已经掌握的键盘盲打技能
      * 已经掌握的计算机软硬件知识和技能
  * 易记性：难忘性，常用，遗忘期，与易学性基本上是重叠的
  * 易用性：操作负荷，稳定期，主要是无法形成条件反射的部分
  * 硬件需求：现在一般不是瓶颈了
  * 软件需求：主要是操作系统，个别软件也有适配问题
* 高效性（有效性）：打字速度（字速），因不同期间而异，可以将错误率折算进来
  1. 码长（键/字，平均码长）：=键速÷字速=键数÷字数。理论极限值，方案值
  2. 键速（键/分，按键速度）：=字速×码长=键数÷时间。人类极限值，个体值。键速里摊入了编码时间和交互时间。为了排除编码时间和交互时间的干扰，在测量基础键速时，可以只测英文打字，而且最好是背下文本后来打字，以排除掉读取时间。
  3. 字速（字/分，打字速度）：=键速÷码长=字数÷时间。
  4. 字数（输入字数），一段时间内的总字数。标点符号、英文字母和阿拉伯数字应加以折算，比如4个才算作1个汉字。
  5. 键数（输入键数），一段时间内的总键数。复合键是不是应该进行折算？
  6. 时间（输入时间），一般以分为单位，有时以秒为单位。入法圈内说的击键指标就是指每秒钟多少次击键，但是字面上容易引起混淆，最好改用按键速度。
* 准确性（可靠性）：错误率，因不同期间而异
* 规范性
  * 语文知识
  * 国家标准
    * GBT 14159-1993 通用键盘汉字编码输入方法评测规则
      * 本地存储位置：D:\SBXLM\标准规范
      * 标准状态：废止

### 实践

#### 传统方案评析

根据评价标准来评析输入方案。

* 搜狗拼音VS五笔字型 | | 搜狗拼音 | 五笔字型 | 备注 | | --- | --- | --- | --- | | 动与静 | 全动态编码 | 全静态编码 | 发展：拼音固顶，五笔调频 | | 编码单位 | 字 | 字词 | 发展：声笔拼音纯顶模式，五笔连打模式 | | 解码单位 | 字词句 | 字词 | 拼音靠全拼首打来提高准确性， | | 平均码长 | 较长，变化大 | 较短，变化小 | 拼音靠简拼重打来缩短码长 | | 易学性 | 门槛很低 | 门槛很高 | 国民教育背景 |
* 搜狗拼音：代表全拼，其它如微软拼音，附带讨论注音
  * 联想、以词定字、即时变换、云词库
  * 动态调频，简拼、混拼
  * 自动分词、辅助码、编码反查
  * 人名模式、单字过滤（0）
  * 选项固定、自定短语、二三候选
  * 引导符号、回车上屏编码（英文）
  * 模糊与容错、纠错、定位修改
  * 快速搜索、翻译等
  * 个性化词库与配置及其多端同步
  * 皮肤、斗图、助聊、助写
* 搜狗笔画：代表笔画，其它如百度笔画
* 自然双拼：代表双拼，其它如小鹤双拼
  * 直接辅助码：辅助当前音节
  * 智能辅助码：辅助之前的任一音节
* 86五笔：代表传统字词，其它如自然码、小鹤音形、二笔音形，附带讨论仓颉
  * 增加简码重数
    * 小鹤音形
    * 九重魔鹤
    * 091五笔
    * 092五笔
  * 缩短全码长度
    * 三码郑
    * C输入
  * 增加全码长度
    * 仓颉

#### 顶功技术应用

* 声笔系列：专精（中文标准键盘串行）特新 （顶功发明、特制程序）
  * 改良方案
    * 声笔拼音
    * 声笔双拼
      * 声笔自然
      * 声笔小鹤
  * 原创方案
    * 声笔简码
    * 声笔飞系
      * 声笔飞单
      * 声笔飞码
      * 声笔飞讯
* 其它方案
  * 西风瘦码
  * 小兮
  * 灵形
  * 星空键道
  * 星空两笔
  * 逸码
  * 小小音形
  * C42
  * 徐码52顶

### 参考

#### 语料工具

* [在线正则工具](https://goregex.cn/)
* [regexr.com](https://regexr.com)
* Excel
* AntConc
* EmEditor
* JupyterLab
* [HanLP](https://github.com/hankcs/HanLP)
* [Jieba](https://github.com/fxsjy/jieba)
* [汉字 Unicode 编码范围](https://www.qqxiuzi.cn/zh/hanzi-unicode-bianma.php)
* [Peter@Norvig.com](https://norvig.com/)
* [GitHub Flavored Markdown Spec](https://github.github.com/gfm/)

#### 在线资料

* [标准下载网](https://www.bzxz.net/bzxz/36945.html)
* [中文](https://baike.baidu.com/item/%E4%B8%AD%E6%96%87/887536)
* [中文信息学报](http://jcip.cipsc.org.cn/)
* [Writing and Civilization: From Ancient Worlds to Modernity](https://www.bilibili.com/video/BV1Me4y1m7aA/?spm\_id\_from=333.337.search-card.all.click\&vd\_source=7d7cd58ef1f2cd5501568b14fe7bc16f)
* [文字书写的历史L'odyssée de l'écriture](https://www.bilibili.com/video/BV1Fa411c77z/?spm\_id\_from=333.337.search-card.all.click\&vd\_source=7d7cd58ef1f2cd5501568b14fe7bc16f)
* [文字之前的记事方式 结绳记事和刻木记事](https://www.bilibili.com/video/BV1C4411M7Zn)
* [史说汉字](https://www.bilibili.com/video/BV1Us411U7Fn/?spm\_id\_from=333.337.search-card.all.click\&vd\_source=7d7cd58ef1f2cd5501568b14fe7bc16f)
* [Thoth's Pill: an Animated History of Writing](https://www.youtube.com/playlist?list=PLc4s09N3L2h3HtaAYVqOVKGt2h6wRasw2)
* [History of Writing](https://en.wikipedia.org/wiki/History\_of\_writing)
* [Printing](https://en.wikipedia.org/wiki/Printing)
* [Typesetting](https://en.wikipedia.org/wiki/Typesetting)
* [History of Communication](https://en.wikipedia.org/wiki/History\_of\_communication)
* [于殿利：文字与文明的起源](https://www.bilibili.com/video/BV1Bv41167K)
* [世界历史 第3集 古代文字的起源](https://www.bilibili.com/video/BV12t411E7yV)
* [楔形文字的起源](https://www.bilibili.com/video/BV18b411G77Q)
* [四川大学霍巍教授：早期文明的起源——偶像、文字与其他](https://www.bilibili.com/video/BV1M14y1s7wH)
* [中文打字机：一个世纪的汉字突围史](https://zhuanlan.zhihu.com/p/612421634?utm\_id=0)
* [Typewriter](https://en.wikipedia.org/wiki/Typewriter)
* [The Chinese Typewriter: A History](https://www.bilibili.com/video/BV1k8411F7Qk)
* [人、语言与机器——《中文打字机》为什么值得书写？墨磊宁 X 徐冰](https://www.bilibili.com/video/BV1aT411a7G5)
* [The Chinese Typewriter: A History](https://www.bilibili.com/video/BV1k8411F7Qk)]
* [惊艳了一个时代的【中文打字机】究竟有多牛？| 万字科普](https://www.bilibili.com/video/BV1k8411F7Qk)
* [Telegraph Code](https://en.wikipedia.org/wiki/Telegraph\_code)
* [Telegraphy](https://en.wikipedia.org/wiki/Telegraphy)
* [Teleprinter](https://en.wikipedia.org/wiki/Teleprinter)
* [概率论](https://www.bilibili.com/video/BV1uY411Y7v1)
* [概率论初步 (by mathematical monk)](https://www.bilibili.com/video/BV1SW411u7VE)
* [数理统计学-缪柏其教授](https://www.bilibili.com/video/BV1zZ4y1S7Em)
* [南开大学 随机过程](https://www.bilibili.com/video/BV19x411p7iB)
* [MIT Stochastic Calculus](https://www.bilibili.com/video/BV1LV4y177XW)
* [信息论（2019年春）台湾交通大学陈伯宁](https://www.bilibili.com/video/BV14N41197bN)
* [Information theory (by mathematical monk)](https://www.bilibili.com/video/BV1SW411u7KY)
* [Principles of Digital Communications-MIT](https://www.bilibili.com/video/BV1tW411w7GD)
* [通信原理趣味动画教程](https://www.bilibili.com/video/BV1Sj411w771)
* [幂律分布告诉你什么是高富帅和白富美-幂律小介绍](https://www.bilibili.com/video/BV1zF411e7sB)
* [媒介域联盟讲座第四季04：Thomas Mullaney 领读The Chinese Typewriter](https://www.bilibili.com/video/BV1r5411976i)
* [数学之美 — 文明之光（全两讲）—主讲人：吴军博士 杨早博士](https://www.bilibili.com/video/BV12p4y1Q7kF)
* [哈工大 关毅《自然语言处理》65讲](https://www.bilibili.com/video/BV1GW411c79R)
* [搜狗输入法官网](https://shurufa.sogou.com/)
* [Windows输入法你了解多少？很多关于搜狗拼音输入法帮你提高效率的功能](https://www.bilibili.com/video/BV1fu411X7TB)
* [深挖win10自带微软拼音输入法。你所不知道的功能，惊呆你的双眼](https://www.bilibili.com/video/BV1Eb4y1t7sG)
* [Microsoft PowerPoint for Beginners: 4-Hour Training Course in PowerPoint 2021/365](https://www.youtube.com/watch?v=LEe8OKhfJWw\&list=RDCMUC-3e3hAUhDV2lwcoQGD2grg\&index=1)
* Images and Videos
  * [https://www.pexels.com/](https://www.pexels.com/)
  * [https://unsplash.com/](https://unsplash.com/)
  * [https://coverr.co/](https://coverr.co/)
* Icons
  * [https://thenounproject.com/](https://thenounproject.com/)
  * [https://ionic.io/ionicons/](https://ionic.io/ionicons/)
* Inspiration
  * [https://www.pinterest.com/](https://www.pinterest.com/)
  * [https://elements.envato.com/](https://elements.envato.com/)
* Fonts
  * [https://www.fontsquirrel.com/](https://www.fontsquirrel.com/)
  * [https://newbird.com/google-fonts/](https://newbird.com/google-fonts/)
  * [https://fontjoy.com/](https://fontjoy.com/)

#### 书籍论文

* 输入法相关
  * 输入模型
    * 汉字编码输入法研究
    * 基于深度学习模型的输入法研究
  * Zipf定律、幂律分布、字词频率
    * 相关概念
      * 频率
        * 绝对
        * 相对
        * 累计
      * 曲线
        * cdf
        * pdf
        * zipf
    * [Wikipedia: Zipf's Law](https://en.wikipedia.org/wiki/Zipf's\_law)
    * [Zipf, Power-laws, and Pareto - a ranking tutorial](https://www.hpl.hp.com/research/idl/papers/ranking/ranking.html)
    * 陶沙. 现代汉语统计频度及其在电脑音轨输入系统中的应用\[J]. 中文信息学报, 1988, 2(1): 61-64
    * 关毅, 王晓龙, 张凯. 现代汉语计算语言模型中语言单位的频度-频级关系\[J}. 中文信息学报, 1999, 13(2): 8-15
    * 游荣彦. Zipf定律与汉字字频分布\[J}. 中文信息学报, 2000, 14(3): 60-65
    * 刘胜久, 李天瑞, 珠杰. Zipf定律与网络信息计量学\[J]. 中文信息学报, 2015, 27(4): 89-94
  * 最短码长、速度上限
    * N元汉字字词编码输入的最短码长和速度上限
  * 其它
    * 二分法在输入法中的应用
* 信息通信相关
  * A Mathematical Theory of Communication
  * Collected Papers of Claude E. Shannon
  * Digital Communications: Source and Channel Coding (I & II)
  * 概率统计
  * How to Lie with Statistics
  * 信息论及其应用

#### 随想灵感

* 从写字到检字：from writing to indexing，写字法→检字法→输入法，写字→检字→打字，写字→印字→打字
* 强关联与弱关联
* 输入就是通信，就是将信息从信源传送到信宿，就是将消息从一个地方传递到另一个地方
* 字→汉字→字符
* 自动补全，字头缩写
* 个性化：基线→特化→同步，基础库→用户库→多设备
* 符号的半角化, 可以避免很多混乱现象, 也便于中西文混合输入与排版. 数字和字母现在已经完全半角化了。

#### 名人名言

* 索绪尔的语言交流模型：普通语言学、背景知识
* 巴甫洛夫的条件反射：心理学、生理学、短期记忆与长期记忆、学习难度
* 香农的通信模型：通信原理、键盘输入与人机协同
* 乔姆斯基的生成语法：形式语言
* 图灵的通用计算机：自动机
* Zipf定律：幂律分布（财富）、帕累托（80-20）法则，尖峰胖尾

#### 标准规范

* GB18030-2022（信息技术：中文编码字符集）
* GBT16295-1996（通用键盘汉字输入技能测试方法）
* GF0023-2020（通用规范汉字笔顺规范）
* GF0017-2013（识字教学用通用键盘汉字字形输入系统评测规则）
* GB/T 16295-1996（通用键盘汉字输入技能测试方法）
* GB/T 2312-1980 （信息交换用汉字编码字符集 基本集）

#### 行业报告

* 艾媒
* 易观
* 比达

#### 网络言论

* 输入法相关
* 打字机相关
* 拉丁化相关
* 拼音相关
* 汉字相关
  * 鲁迅：1936年10月，鲁迅临逝世前，在答《病中答救亡情报访员》时候说："汉字不灭，中国必亡。"
  * 毛泽东：文字必须改革，必须走世界文字共同的拼音方向。

#### 输入方式

* 键盘输入
* 语音输入
* 手写输入
* 鼠标输入（点点输入）

#### 输入法模式

* 传统
  * 拼音
  * 五笔
  * 仓颉
  * 注音
* 顶功
  * 声笔拼音
  * 声笔双拼
  * 声笔简码
  * 声笔飞系

#### 输入法品牌

* 搜狗
* 百度
* 讯飞
* 微软
* 声笔

#### 输入法平台

* Rime
* 多多
* 小小

#### 打字练习

* 金山打字通
* 极速云跟打

#### 输入法安全

* 隐私泄露
* 数据安全

#### 输入法商机

* 直接方式
  * 直接收费
  * 数据同步
* 间接方式
  * 广告
  * 三级火箭
  * 用户数据

#### 编码理论

1. 信息论
   1. 信息熵、信道容量
   2. 等长、变长
   3. 有记忆、无记忆
   4. 有损、无损
   5. 唯一可译、唯一可分
2. 通信实践
   1. 信源编码
      1. 无损编码
         1. 熵编码
            1. Huffman码
            2. Shannon码
            3. Fano码
            4. Shannon-Fano-Elias码
            5. 算术码
         2. 字典编码
            1. LZ77
            2. LZ78
            3. LZW码
               1. Wikipedia: [Lempel–Ziv–Welch](https://en.wikipedia.org/wiki/Lempel%E2%80%93Ziv%E2%80%93Welch)
               2. B站: [LZW压缩算法](https://www.bilibili.com/video/BV1Ds411G7p7)
      2. 有损编码
         1. PCM
         2. 预测编码
         3. 变换编码
         4. 插值和外推法
         5. 统计编码
         6. 矢量量化和子带编码
   2. 信道编码
      1. Hamming Code
      2. Reed Soloman Code
      3. Turbo Code
      4. Polar Code
3. 文件压缩
   1. 图像
   2. 声音
   3. 视频
   4. 文字

![image.png](https://cdn.nlark.com/yuque/0/2023/png/38725348/1693186006257-a15278a6-9a9f-4cab-a5ba-189abce24f9b.png#averageHue=%23f8f7e2\&clientId=u7fd03dde-2401-4\&from=paste\&height=595\&id=uc3127d50\&originHeight=595\&originWidth=933\&originalType=binary\&ratio=1\&rotation=0\&showTitle=false\&size=122643\&status=done\&style=none\&taskId=uaf8ca7a5-bd99-4496-b8fa-ae2ab8038bb\&title=\&width=933)
