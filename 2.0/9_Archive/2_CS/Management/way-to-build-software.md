# 构建之法：现代软件工程

我成了一名职业程序员，但是我发现所有的算法别人都已经实现了，我只要调用就可以。似乎我们公司的软件与数据结构、算法的关系都不大。那我当初辛辛苦苦学习的数据结构和算法有用么？如何区分一个好的程序员和不好的程序员呢？

---

程序，在这里指的是源程序，就是一行行的代码。仔细看过去，它们的确是建立在数据结构上的一些算法。程序还要对数据进行操作，这些数据有些是静态的（例如软件的图标、提示信息），有些是动态的（例如程序生成的随机数字、程序通过网络下载的数据、用户的文字或语音输入等）。但是光有代码和静态数据还是不行，工程师要把它们构建为机器能懂的可执行代码。构建不仅仅是cc和link命令，一个复杂的软件不但要有合理的软件架构（Software Architecture）、软件设计与实现（Software Design, Implementation and Debug），还要有各种文件和数据来描述各个程序文件之间的依赖关系、编译参数、链接参数，等等。这些都是软件构建的过程。软件团队的成员每天都在修改各种源代码，怎么保证软件在修改过程中能不断提高质量，至少要维持以前的质量，不至于崩溃？有些时候，我们要为某个需求写一些特殊功能，不久后又要把这些功能再合并回主要版本。有些程序要配置不同的界面，运行在中文、英文或其他语言的操作系统上；有些程序还有32位版本、64位版本等。这是源代码管理（Source Code Control）的问题—有时候也叫配置管理（Software Configuration Management）。我们还有一系列的工具和程序来保证程序的正确性，这些工具流程和程序本身应该更正确，才能保证别的软件的质量。这就是质量保障（Quality Assurance），具体的验证过程叫做软件测试（Testing）。一个软件或者服务要有人买，就得找到顾客，顾客有各种需求，有些靠谱，有些不靠谱；有些容易做到，有些难以做到。软件团队要从需求分析（Re-quirement Analysis）开始，把合适的需求梳理出来，然后逐步展开后续工作，如设计（软件架构）、实现（写数据结构和算法）、测试，到最后发布软件。软件团队的人员也会流动，新的成员要尽快读懂已有的程序，了解程序的设计，这叫程序理解（Pro-gram Comprehension）。软件在运行过程中还会出这样那样的问题，也许我们要时不时给软件打一个补丁，或者维护众多的服务器，团队的新老成员要一起工作，修复各种各样的问题，这叫软件维护（Software Maintenance），或者服务运营（Service Operation）。这一系列过程就是软件的生命周期（Software Life Cycle，SLC），有人得负责软件项目的管理（Project Management）。一个好的软件，即使功能和同类软件区别不大，但是会让人感觉到非常好用。这就是软件的用户体验（User Experience）。用户体验和数据结构、算法没有直接的关系，但是很多非常成功的软件就赢在这个方面。

---

软件开发过程有什么特别的难题？学者们总结了下面五点：

1. 复杂性（Complexity） 软件可以说是人类创造的最复杂的系统类型。大型软件（操作系统、办公软件、搜索引擎）有超过百万行的源代码，上万个不同的文件。而软件工程师通常一次只能看到30—80行源代码（相当于显示器的一屏），他们的智力、记忆力和常人差不多。软件的各个模块之间有各种显性或隐性的依赖关系，随着系统的成长和模块的增多，这些关系的数量往往以几何级数的速度增长。
2. 不可见性（Invisibility） 软件工程师能直接看见源代码，但是源代码不是软件本身。软件以机器码的形式高速运行，还可能在几个CPU核上同时运行，工程师是“看”不到自己的源代码如何具体地在用户的机器上被执行的。商用软件出现了错误，工程师可以看到程序在出错的一瞬间留下的一些痕迹（错误代号、大致的目标代码位置、错误信息），但是几乎无法完整重现到底程序出现了什么问题。
3. 易变性（Changeability） 软件看上去很容易修改，修改软件比修改硬件容易多了。人们自然地期待软件能在下面两种情况下“改变”： a) 让软件做新的事情；b) 让软件适应新的硬件。但是与此同时，正确地修改软件是一件很困难的事情。
4. 服从性（Conformity） 软件不能独立存在，它总是要运行在硬件上面，它要服从系统中其他组成部分的要求，它还要服从用户的要求、行业系统的要求（例如银行利率的变化）。
5. 非连续性（Discontinuity） 人们比较容易理解连续的系统：增加输入，就能看到相应输出的增加。但是许多软件系统却没有这样的特性，有时输入上很小的变化，会引起输出上极大的变化。

---

计算机科学（Computer Sci-ence）这一学术领域可以分为下面这些领域： 计算理论（Theoretical Computing） 信息和编码理论（Information and Coding The-ory） 算法和数据结构（Algorithm and Data Struc-ture） 形式化方法（Formal Methods） 程序设计语言（Programming Language）

偏实践的领域： 计算机体系结构（Computer Architecture） 并行计算和分布式系统（Concurrent, Parallel and Distributed System） 实时系统和嵌入式系统（Real Time and Embed-ded System） 操作系统（Operating System） 计算机网络（Networking） 科学计算（Scientific Computing） 安全和密码学（Security and Cryptography）

人工智能（Artificial Intelligence） 这个领域涵盖了许多相关的领域，如模式识别（Pattern Recognition）、机器学习（MachineLearning）、数据挖掘（Data Mining）、信息提取（Information Retrieval）等。 计算机图形学（Computer Graphics）、计算机视觉（Computer Vision）、 多媒体（Multimedia） 数据库和大规模数据处理（Database and Large Scale Data Processing） 万维网（World Wide Web） 自然语言处理和语音（Natural Language Pro-cessing and Speech） 人机交互（Human Computer Interaction） 软件工程（Software ngineering）

---

人类文明要向前发展，离不开思考、发现、构建。我曾经在微软亚洲研究院技术创新部工作过七年，我所在的工程团队和很多计算机科学家在不同领域一起做项目，这些项目各有特点：

+ Build To Learn：开发软件，构建系统的目的是做进一步的试验，试图发现客观规律或探求某方法的优劣。这些项目经常是科研论文的基础工作。
+ Build To Show：为了突出地展现某个技术的作用，开发一些以演示为目的的软件，这些项目很吸引眼球，经常获得新闻报道，但是功能未必全面。
+ Build To Serve：为了服务一定范围的目标用户而构建的工具等，有时以公开SDK的形式发布。
+ Build To Win：以在市场上赢得用户为目标而构建的软件。这也是种种科学发现、技术突破最好的试金石。

---

一个团队需要一定的流程来管理开发活动，每个工程师在软件生命周期所做的工作也应该有一个流程，这一章会介绍PSP（Personal Software Pro-cess，个人软件开发流程）。

---

如何能让自己负责的模块功能定义尽量明确，模块内部的改变不会影响其他模块，而且模块的质量能得到稳定的、量化的保证？单元测试就是一个很有效的解决方案。

---

卡内基梅隆大学（CMU）的能力成熟度模型（CMM和CMMI），是用来衡量一个团队能力的一套模型。CMU的专家们针对软件工程师也有一套模型，叫Personal Software Process（PSP），PSP和任何其他方法论一样，也不是一蹴而就的。

---

现代软件产业经过几十年的发展，一个软件由一个人单枪匹马完成，已经很少见了，软件都是在相互合作中完成的。合作的最小单位是两个人，两个工程师在一起，做的最多的事情就是“看代码”，每人都能看“别人的代码”，并发表意见。但是每个人对于什么是“好”的代码规范未必认同，这时我们很有必要给出一个基准线—什么是好的代码规范和设计规范。程序员写的代码是给人看的，还是给机器看的？人也看，机器也看，但是最终是人在看。我们的代码要让“旁观者”看得清清楚楚。

---

做一个有商业价值的项目，或者在团队里工作，代码规范相当重要。“代码规范”可以分成两个部分： 1. 代码风格规范。主要是文字上的规定，看似表面文章，实际上非常重要。 2. 代码设计规范。牵涉到程序设计、模块之间的关系、设计模式等方方面面的通用原则。

---

代码风格的原则是：简明，易读，无二义性。提示：这里谈的风格是一家之言，如遇争执，关键是要本着“保持简明，让代码更容易读”的原则，看看争执中的代码规范能否让程序员们更好地理解和维护程序。

---

是用Tab键好，还是2、4、8个空格？ 结论：4个空格，在Visual Studio和其他的一些编辑工具中都可以定义Tab键扩展成为几个空格键。不用Tab键的理由是，Tab键在不同的情况下会显示不同的长度，严重干扰阅读体验。4个空格的距离从可读性来说，正好

---

行宽必须限制，但是以前有些文档规定的80字符行宽太小了（以前的计算机/打字机显示行宽为80字符），现在时代不同了，可以限定为100字符。

---

如果我们做的项目是真实的，有具体而多变的需求，有工期、质量和资源的矛盾，团队成员各自的水平、目标也不一致，那么团队内部不可能没有矛盾。但是，矛盾不是一开始就爆发的，它有自己的生命周期，有不同的发展阶段。谈恋爱、两人合作项目，都有相似的几个阶段，下面我们以生活中的跳交谊舞为例，描述一下两人合作的各个阶段。

1. 萌芽阶段（Forming） 以跳舞为例，两人刚认识时，拘谨而彬彬有礼。这一阶段的现象：两人刚刚互相认识，这时大家都有礼貌，一般交流不少，每个人都想得到对方的接纳，试图避免冲突和容易引起挑战的观点。对即将进行的舞蹈，有不同的期望值，但是双方彼此并不了解。
2. 磨合阶段（Storming） 开始跳舞，开始踩脚。接触之后，才感到手足无措，眼睛不知往哪里看，才能感受到对方原来舞步是这样的……这样的笨拙。
3. 规范阶段（Norming） 跳舞逐渐和谐、合拍，团队成员就很多事情取得了一致。一些成文或不成文的规则逐步建立起来了。男方轻轻的一个手势，女方就知道如何旋转。
4. 创造阶段（Performing） 跳舞二人合而为一，为艺术而舞蹈（大家发出了唏嘘向往之声）。并不是所有的合作都能达到这一阶段，磨合太多后，我们还可能进入“解体阶段”。
5. 解体阶段（Deforming） 散伙，各走各的独木桥，回宿舍抱着板凳跳舞，或者另找舞伴。

---

可以看出，这些团队有共同的特点： 1. 团队有一致的集体目标，团队要一起完成这目标。一个团队的成员不一定要同时工作，例如接力赛跑。（王屋村搬砖的“非团队”成员则不然，每个人想搬多少就搬多少，不想干了就结算工钱走人。） 2. 团队成员有各自的分工，互相依赖合作，共同完成任务。（王屋村搬砖的“非团队”成员则是各自行动，独立把任务完成，有人不辞而别，对其他的搬砖人无实质影响。）

---

主治医师模式（Chief Programmer Team，Surgical Team） 就像在手术台上那样，有一个主刀医师，其他人（麻醉，护士，器械）各司其职，为主刀医师服务。这样的软件团队中，有首席程序员（Chief Pro-grammer），他/她负责处理主要模块的设计和编码，其他成员从各种角度支持他/她的工作（后备程序员、系统管理员、工具开发、编程语言专家、业务专家）。佛瑞德·布鲁克斯（Frederic BrooksJr.）在主管IBM System360项目时就采用了这种模式。在一些学校里，软件工程的团队模式往往从这一模式退化为“一个学生干活，其余学生跟着打酱油”。

---

明星模式（Super-star Model） 主治医师模式运用到极点，可以蜕化为明星模式，在这里，明星的光芒盖过了团队其他人的总和，2004年到2012年的“翔之队”就是一个例子。明星也是人，也会受伤，犯错误，如何让团队的利益最大化，而不是明星的利益最大化？如何让团队的价值在明星陨落之后仍然能够保持？是这个模式要解决的问题。真正有巨大成就的明星都能意识到团队的作用，迈克尔·乔丹说过，“Talent winsgames, team work wins championship.”

---

社区模式（Community Model） 社区由很多志愿者参与，每个人参与自己感兴趣的项目，贡献力量，大部分人不拿报酬。这种模式的好处是“众人拾柴火焰高”，但是如果大家都只来烤火，不去拾柴；或者捡到的柴火质量太差，最后火也就熄灭了。“社区”并不意味着“随意”，一些成功的社区项目（例如开发和维护Linux操作系统的社区），都有很严格的代码复审和签入的质量控制。

---

业余剧团模式（Amateur Theater Team） 这样的团队在每一个项目（剧目）中，不同的人会挑选不同的角色。在下一个剧目中，这些人也许会换一个完全不同的角色类型。各人在团队中听从一个中央指挥（导演）的指导和安排。在学生实践项目或培训项目中，这样的事情经常发生。

---

秘密团队（Skunk Work Team） 一些软件项目在秘密状态下进行，别人不知道他们具体在做什么。苹果公司1980年代在研发Macin-tosh之后的系统时，就有两三个团队在不同时期进入秘密状态开发。21世纪的一些创业团队也是处于类似状态。这种模式的好处是：团队内部有极大的自由，没有外界的干扰（不用每周给别人介绍项目进展，听领导的最新指示，等等），团队成员有极大的投入。

---

特工团队（SWAT） 就像电影电视中的特工组《加里森敢死队》等一样，软件行业的一些团队由一些有特殊技能的专业人士组成，负责解决一些棘手而有紧迫性的问题。例如2000年之前，很多公司都需要专业人士去解决Y2K问题。这些团队成员必须了解传统语言和老式系统，才能胜任这样的任务。现在还有一些专门做网站安全性服务的团队，也属于这一类型。

---

想象一下交响乐团的演奏，有下面的特点。 家伙多，门类齐全。 各司其职，各自有专门场地，演奏期间没有聊天、走动等现象。 演奏都靠谱，同时看指挥的。 演奏的都是练习过多次的曲目，重在执行。

---

交响乐团模式（Orchestra） 想象一下交响乐团的演奏，有下面的特点。 家伙多，门类齐全。 各司其职，各自有专门场地，演奏期间没有聊天、走动等现象。 演奏都靠谱，同时看指挥的。 演奏的都是练习过多次的曲目，重在执行。

---

爵士乐模式（Jazz Band） 爵士乐是另外一种演奏模式，我们观察这个视频（So What）[注释2]来体会一下爵士乐的代表人物迈尔斯·戴维斯（Miles Davis）[注释3]领导的乐队的演奏方式。

---

从外行看热闹的角度看，和交响乐团相比，这种模式有以下特点。 不靠谱。他们演奏时都没有谱子。 没有现场指挥，平时有编曲起到协调和指导作用（和迈尔斯合作的编曲吉尔·伊文斯（GilEvans）也是很有造诣的音乐家）。 也有模式，迈尔斯（姑且称之为架构师）先吹出主题，然后他走到一旁抽烟去了，其余人员根据这个主题各自即兴发挥；最后迈尔斯加入，回应主题，像是对曲子的总结。 人数较少。评论家归纳迈尔斯·戴维斯的特点是： individual expression, emphatic interac-tion, and creative response to shifting con-tents. 强调个性化的表达，强有力的互动，对变化的内容有创意的回应。这看上去跟“敏捷的开发模式”有点类似。这样的团队模式和上面的“交响乐团模式”在很多方面都对立，但是两种模式都产生了很受欢迎的音乐作品，因此不能简单地说孰优孰劣。

---

功能团队模式（Feature Team） 很多软件公司的团队最后都演变成功能团队，简而言之，就是具备不同能力的同事们平等协作，共同完成一个功能。

---

官僚模式（Bureaucratic Model） 还有一个团队模式可以叫官僚模式。

这种模式脱胎于大机构的组织架构，几个人报告给一个小头目，几个小头目报告给中头目，依次而上。这种模式在软件开发中会出问题。因为成员之间不光有技术方面的合作和领导，同时还混进了组织上的领导和被领导关系。跨组织的合作变得比较困难，因为各自头顶上都有不同的老板。这种模式如果应用不好，最后会变成“老板驱动”的开发流程，见后面的介绍。

---

写了再改模式（Code-and-Fix） 史蒂夫·迈克康奈尔（Steve McConnell）在这里提到了不少开发流程。第一个提到的开发流程——Code-and-Fix，看起来和一窝蜂团队模式非常像

---

瀑布模型（Waterfall Model） 当软件行业还在年幼的时期，它从别的成熟行业（硬件设计，建筑工程）借用了不少经验和模型。在那些“硬”的行业中，产品大多遵循 [分析→设计→实现（制造）→销售→维护] 这个流程。由于在“硬”行业中产品一旦大规模生产，要再返回去修改时就非常困难，甚至是不可能的。因此这个模型描述了单向的、不可逆的生产过程。

---

Rational Unified Process 统一流程（RUP）从瀑布模型开始的各种模型都有一个共同点：重计划，重事先设计，重文档表达。这一类的方法中集大成者要算Rational统一流程（Rational UnifiedProcess，RUP）[注释5]。RUP把软件开发的各个阶段整合在一个统一的框架里。要完成一个复杂的软件项目，团队的各种成员要在不同阶段做不同的事情，这些不同类型的工作在RUP中叫做规程（Discipline）或者工作流（Workflow）

---

老板驱动的流程（Boss-Driven Process） 笔者在和中国一些企业的软件开发者交流的时候，听闻不少人提到开发流程事实上是由行政领导主导，或者由公司的老板驱动，我们姑且把它命名为老板驱动的流程（Boss-Driven Process）。

---

渐进交付的流程（Evolutionary Delivery），MVP和MBP 这个流程是史蒂夫·迈克康奈尔（Steve McConnell）在1996年总结的，但是它其实已经很接近现在大家谈论较多的迭代式开发流程。当系统的主要需求和架构明确之后，软件团队进入了一个不断演进的evolution循环中：[开发→发布→听取反馈→根据反馈做改进]

---

敏捷开发原则
1. 尽早并持续地交付有价值的软件以满足顾客需求
2. 敏捷流程欢迎需求的变化，并利用这种变化来提高用户的竞争优势
3. 经常发布可用的软件，发布间隔可以从几周到几个月，能短则短
4. 业务人员和开发人员在项目开发过程中应该每天共同工作
5. 以有进取心的人为项目核心，充分支持信任他们
6. 无论团队内外，面对面的交流始终是最有效的沟通方式
7. 可用的软件是衡量项目进展的主要指标
8. 敏捷流程应能保持可持续的发展。领导、团队和用户应该能按照目前的步调持续合作下去
9. 只有不断关注技术和设计，才能越来越敏捷
10. 保持简明—尽可能简化工作量的技艺—极为重要
11. 只有能自我管理的团队才能创造优秀的架构、需求和设计
12. 时时总结如何提高团队效率，并付诸行动

---

敏捷流程的经验教训 这里有一些实践者的经验教训：

1. 敏捷宣言表明的是一些优先级，不必当作圣旨或者教条来争论。
2. Scrum Master不是一个官，而是一个没有行政权力的沟通者，就像微软的PM那样。他/她同时还要在团队中做具体的工作。直接把原来的“经理”变成Scrum Master，大多行不通。
3. 一些项目需要很多暗箱操作和政治角力才能搞定，Scrum会把这些矛盾都摆到明处。这有好处，也有风险。
4. 在复杂的项目里，要让一线团队成员做决定。
5. 创业公司的团队其实经常是运行在Scrum 的模式中（只不过大家太忙，没工夫论证自己到底有多么Scrum）。
6. 在Scrum计划阶段的估计不是一个“合同”，领导们不要把它当成一个合同。估计总是不准的。坚持短期的Sprint，这样即使不准的估计也不会有大的损害。
7. 不要和管理层谈“流程”，他们只关心“结果”。
8. 在大型团队、跨地区的团队，或者复杂项目中，Scrum并没有非常完美的答案，Scrum的创始人也承认这一点。

---

MSF没有像敏捷那样搞一个宣言，但是它也有一套思想框架—9条基本原则

1. 推动信息共享与沟通（Foster open communications）
2. 为共同的远景而工作（Work toward a shared vision）
3. 充分授权和信任（Empower team members）
4. 各司其职，对项目共同负责（Establish clear accountability and shared responsibility）
5. 交付增量的价值（Deliver incremental value）
6. 保持敏捷，预期和适应变化（Stay agile, expect and adapt change）
7. 投资质量（Invest in quality）
8. 学习所有的经验（Learn from all experiences）
9. 与顾客合作（Partner with internal and external customers

---

软件团队里除了能写代码、测试代码和画图做设计的成员，还有一类角色，不做上面这些事情但也很重要，我们叫他们项目经理——PM。PM的M就是Manager，但是P有这几种：Prod-uct Manager、Project Manager、Program Man-ager，在不同的行业和公司，他们的作用各不相同。这一章主要介绍微软的项目经理——ProgramManager。Product Manager：产品经理——正确地做产品。目前国内公司大部分PM都是指这个职位。产品经理对一个或多个产品或产品线负责，而互联网产品涉及到这些方方面面：产品定位、市场发展、需求分析、运营、营销、市场推广、商务合作。产品经理横跨这些部门，寻找资源，持续推进产品。随着产品的发展，不同公司，对PM要求会不一样。核心要求是，根据市场和用户需求，协调各部门资源，正确地把握产品定位和方向，解决用户的痛点，持续优化产品

---

Project Manager：项目经理——正确地做流程。在某些公司，这个职位与产品经理分开单列。他们对项目流程负责，即项目从立项到上线按时完成。正确地协调团队内部外部，调配各部门资源和时间，有效进行风险管理，保证一个项目顺利按计划结项，是一个项目经理的核心价值

---

Program Manager：微软的职位名称。微软产品团队三足鼎立的角色分配就是PM、开发、测试。PM负责除产品开发和测试之外的所有事情。从某种意义上说，是前面两种角色的综合。微软通常有专门的产品策划（Product Planner），他们和市场部门的专职人员一起，负责产品的长期发展和市场推广。

---

随着业务的发展和团队的壮大，下面这两个问题凸显出来：

1. 团队成员之间交流的成本急剧增长
2. 有很多开发和测试之外的事情，需要专人负责

---

些同学说，我写的代码都不用测试，我真想不到除了开发和测试之外，还有什么事情可做。我们看看微软公司有哪几类PM。 有做功能设计的PM；有些功能或产品需要深入掌握各个计算机科学分支的专业知识才能做好。例如Visual Studio中的各种计算机语言、框架、TFS的项目的项目经理，SQL Server、Windows Server、Azure、Bing Search核心算法等团队的PM 有些PM需要对商业和客户有很强的了解能力，例如Office办公软件的PM 有些PM需要具备广泛的经验和知识面，以及商业拓展能力，例如互联网MSN部门的PM 有些是驱动流程的PM，例如推动几百人的团队完成一个版本的开发，又如保证WindowsPhone在能在几十种不同硬件上发布 也有专门深入某一领域的PM，例如负责软件的国际化/本地化（Globalization/Localiza-tion） 还有和研究人员合作，琢磨如何将前沿技术引入主流产品，做技术转化的PM

---

成为一个合格的PM，需要哪些能力呢？

1. 观察、理解和快速学习能力PM要能够在一个新的领域中很快上手。PM要能理解用户，能站在用户的角度上考虑问题，观察发现用户不善于表达的需求，体察团队成员的言外之意，倾听老板/客户/利益相关人的弦外之音。要有能够理解别人的处境、心理、动机的能力——同理心。一个PM平时或许能玩转很多高技术的工具，但是当工作需要时，他/她能突然把自己变成一个完全不懂技术的菜鸟用户，从用户的角度来看问题。
2. 分析管理能力每天项目中发生的事情千头万绪，PM要能够分析出重点，找到优先级，做判断、做决定……
3. 一定的专业能力如果一定要说专业能力的话，PM的专业就是理解和表达，你能否理解不同人的心理、需求和言外之意？你能否借助文字、图表、草图，甚至代码来清晰准确地表达自己的想法？PM 要始终能满怀激情地向用户兜售产品，向团队兜售希望。PM通常也能写代码，能玩转Excel、PPT、Visio、甘特图，会PS，有文字功底，写的博客有人爱读，反正，总得有几招绝活吧！不用说还要有大量的阅读，对IT行业、用户心理、社会都要有广泛的了解。
4. 自省的能力。一个PM做第一个项目时可以拍脑袋定工期，拍胸脯打包票，最后拍屁股走人（谁没年轻过呢），但是失败之后要有自省和自我改进的能力。在生活中能不能锻炼PM的能力呢？当然可以，比如装修房子、组织一个大型活动、带自己的孩子、帮邻居家带三天孩子，等等。

---

在一个项目中，PM的具体任务是什么呢？他们的任务是：

1. 带领团队形成团队的目标/远景，把抽象的目标转化为可执行的、具体的、优美的设计；
2. 管理软件的具体功能的生命周期（需求/设想/设计/实现/测试/修改/发布/升级/迁移/淘汰）；
3. 创建并维护软件的规格说明书，让它成为开发/测试人员及时准确的指导，而不是障碍；
4. 代表客户和用户的利益，主动收集用户反馈，预期用户新的需求。协调并决定各种需求的优先级；
5. 分析并带领其他成员对缺陷/变更需求形成一致意见，并确保实施；
6. 带领其他成员确保项目保持功能/时间/资源的合理平衡，跟踪项目进展，确保团队发布令客户满意的软件；
7. 收集团队项目管理和软件工程的各种数据，客观分析项目实施过程中的优缺点，推动项目成员持续改进，从而提振士气。

---

其实，计算机软件的用户界面（User Interface，UI）和用户体验（User eX-perience，UX）是一个有着丰富内容的学术领域，软件工程师们在长期工作中也积累了很多相关的经验

---

诺尔曼进一步阐明了设计的三个层次，以及对应的产品特性：本能（Visceral）层次的设计——外形行为（Behavior）层次的设计——使用的乐趣和效率反思（Reflective）层次的设计——自我形象、个人满足感、回忆三个层次的因素相互交织，共同影响了用户体验。大部分软件工程师主要关心的是“使用的效率”，这只是用户体验设计的很小的一部分。

---

1. 尽快提供可感触的反馈系统状态 要有反馈，等待时间要合适。现在程序发生了什么，应该在某一个统一的地方清晰地标示出来。一个目标用户能够只靠软件的主要反馈来完成基本的操作，而不用事先学习使用手册。系统的反馈可以是视觉的、听觉的、触觉的（例如手机振动）。但是要避免简单重复的提示。
2. 系统界面符合用户的现实惯例（Familiarity，Avoid Surprise） 与用户沟通，软件系统要使用用户语言而不是开发者语言，所用的概念要贴近生活实际，而不是用学术概念或开发者的概念。我们说的生活实际，最好是目标用户的实际生活体验。例如，给病人使用的网络挂号系统，就不宜使用只有医务工作者才熟悉的术语和界面（最坏的结果是使用软件工程师才熟悉的术语和界面，而医护人员和病人对此很不熟悉）软件的反馈要避免带给用户惊奇——例如，在用户没有期待对话框的时候，软件从奇怪的角度弹出对话框，或者给用户提示“找不到对象”。
3. 用户有控制权 操作失误可回退，要让用户可以退出软件（很多软件都没有退出菜单，这是导致用户反感的一大原因）。用户可以定制显示信息的多少，还可以定制常用的设置。
4. 一致性和标准化 在软件中，对同一事物和同类操作的表示用语，各处要保持一致。例如，某词典软件有“帮助用户收集生词并且背诵生词”的功能。这个功能要有明确一致的称呼，不能混杂着叫“单词本”、“生词本”、“Word List”、“Word Book”、“单词文件”……等等。
5. 适合各种类型的用户 我们的软件要为新手和专家提供可定制化的设计。一些操作方式，如快捷操作，用户可以自行调整。我们还应该为存在某些障碍的用户（色弱、色盲、盲人、听力有缺陷的用户、操作键盘鼠标不方便的用户等）提供一定程度的便利。对于长期使用某个软件的用户，软件应该能适应用户的使用习惯，让用户越用越顺手，最后产生感情上的好感和忠诚度。
6. 帮助用户识别、诊断并修复错误 软件的关键操作要有确认提示，以便帮助用户及早消除误操作。要注意使用朴素的语言来表述错误信息。错误信息需要给出下一步操作提示（我现在出错了，那下一步怎么办）。必要时提供详细的帮助信息，并协助用户方便地从错误中恢复工作。让所有的用户都可以通过电子邮件或者表单来提交反馈意见。有些程序用一对简单的笑脸/哭脸符号来鼓励用户提交反馈，这也是很好的办法。
7. 有必要的提示和帮助文档 不需要文档，用户就能使用自如，当然更好，必要时还可以提供在线帮助。如果软件和用户的工作相关（而不是简单的游戏），那么基本的提示和帮助文档还是很有必要的，而且也要提供便利的检索功能。文档要从用户的角度出发描述具体步骤，并且不要太冗长。有些软件在首次启动时会通过图示或动画展现某些新功能的用法，或引导用户进行一些基本的设置（例如第一次使用输入法时，让用户选择候选词的个数、字体大小，等等）。这些都是不错的方法。在PC桌面软件时代，软件团队总是要等到项目的稳定阶段才开始写“帮助文档”，因为之前的软件界面和功能还有很多变化，然后要很快写好，才能和软件一起发布。在互联网时代，离线的帮助文档进步到“联机帮助”网页；在大量带宽和活跃的用户社区帮助下，我们可以看到用户创造的如何高效使用各种软件的视频。这应该给软件团队很多启发——如何能用好各种形式的“帮助文件”

---

在我们熟悉的计算机和IT领域，所有我们看到的“酷”的东西，都是几代人、许多团队前赴后继持续创新的结果。就像拼图一样，很多聪明人都模糊地看出了最终图像，都在一块一块地拼接，往往拼好最后一块的人得到了最大的荣誉。但是没有前人的积累，没有自身扎实的功力，就没有“最后一块”等着大家去拼。另一个推论是——不要一开始就想着找到并拼对所有的拼图块，以为能够打造一个巨大的创新。彼得·德鲁克（Peter Drucker）说过： Those entrepreneurs who start out with the idea that they'll make it big – and in a hurry – can be guaranteed failure.

---

框架介绍：SWOT分析 任何公司的产品都不是十全十美，被用户永远追捧。产品在市场上和别人竞争，有很多因素要考虑，这里有一个简单的SWOT表格帮助软件团队成员分析。表中的“机会”可以是小的、暂时的机会（如不久会有一个手机游戏大奖赛，我们可以为之定制游戏，争取获奖以提高知名度）；也可以是大的、长期的机会（如整个用户群体从PC桌面向手机迁移，我们原来的桌面文字处理软件可以争取在手机上获得先发优势）；还可以是和政策相关的机会（如某国政策放宽对私人信贷的监管，或对于游戏产业有新规定等）。

---

动量（Momentum）和加速度（Acceleration） 一列火车拖着几十节车厢在行驶，引擎已经停止提供动力，它会越来越慢，它的动能还是很大的，但是加速度为负值。一架飞机在跑道上缓缓启动，速度较慢，但是加速度很大，常识告诉我们它将会以很大的动量起飞。在IT行业也有这样的现象，例如一个公司维护着有很长历史的PC桌面版软件，它每年都能带来大量的收入，虽然逐渐在减少，但是依然可观。公司还开发了一个移动端软件，它历史短，还没有赚钱，但是用户量上升很快，但是绝对数目还是远小

---

萌芽阶段 萌芽阶段（Forming），就像小苗破土而出，柔弱但充满希望。在这一时期，团队成员刚刚接触到团队的宗旨，同时很可能刚刚互相认识。团队的目标没有真正达成一致，而成员则非常依赖于团队领导的指导。其他特征如下。 1. 个人的角色和职责不清楚，做事的规程往往被忽略。 2. 这时大家都很有礼貌，一般交流不少，每个人可能都想得到队友的接纳，试图避免冲突和容易引起挑战的观点。团队的成员在有意无意地探知同伴和领导的做事方式和容忍度。 3. 成员也在琢磨任务到底有多大，怎么去完成它。 4. 每个人都忙着适应环境、团队结构、角色、日常流程等。有鉴于此，严重的问题不一定能够及时地提出来讨论。重要的事情并不能够真正得到解决。 5. 开始各种各样的讨论。成员们对于组织结构有不少看法，对完成任务的困难也有不少讨论，但是还没有把注意力集中到解决问题上。 在这一时期，领导要回答很多问题：我们要做什么，怎么做，如何才是成功，与其他团队是什么样的关系，等等。由于百废待兴，没有太多时间进行详细的讨论以达成共识，因此，领导要快刀斩乱麻地决定一些重要的问题，让团队在短时间内看到一些成果。

---

磨合阶段 磨合阶段（Storming）就像一个人的青少年时期，充满了对个人、同伴和团队的疑惑和冲突。团队中的一团和气只能维持一小段时间，大家不得不认真地面对问题，开展讨论。随着讨论的深入，有些人会沉不住气，就会出现小的意见分歧和冲突。这些冲突不一定都是技术问题，也许是关于角色、职责、相互关系，甚至是各自性格、文化的冲突。这时，成员之间会出现竞争，不少人都想成为某个领域的“拥有者”（在软件项目中，谁负责哪方面，每个方面要怎么做，等等）。同时也有一些人以不同的方式进行挑战。也许会形成小团体，甚至有权力斗争。有人专注于解决问题，有人喜欢“与人斗，其乐无穷”，有人想回到当初一团和气的阶段。冲突的结果是有人觉得自己“赢了”，有人反之。有时即使大家有相同的论点，还是有争论（因为大家想充分表达自己）。这个阶段还有一种现象，即开会时谁嗓门大，谁往往会赢。在团队中解决争端，有下面的几种方法，各有利弊： 追求最大和谐，达到全体共识（Consensus）：好处是大家能同心协力行动，坏处是需要很长时间才能达到共识，也许达到不了。 投票（Voting）：好处是能较快地形成结论，坏处是投票会产生一些赢家和输家，输家总是不太满意，如果处理不好，会导致对立。 咨询（Consulting），由领导私下和几位专家讨论，形成决定：团队的其他成员也许会有不被重视的感觉。 独裁（Dictatorship）：领导很爽，但是副作用较多。 交换决定权（Trade Off）：几个主要角色的代表轮流做决定，行使独裁权。这个模式执行起来也许会让团队的方向游移不定。 这个时期最有可能出现谣言和误解，对此，团队领导最好让矛盾和分歧充分地暴露，将各种冲突公开化，并且学会倾听、理解和调整。有时候，团队领导不得不妥协，以便项目继续向前推进，因为没有时间去说服每个人，从而得到最优结果。积极、公开的信息流动是消除谣言和误解的最好方式。

---

领导在这个阶段会发现成员的一些特点，要区别对待，例如：

1. 对于技术能力强，并且通过实际工作得到大家认可的成员，应鼓励他们发挥更多技术领导作用。
2. 对一些经常持有不同意见、特立独行、看似拖团队后腿的成员，这时不应该妄下判断，其实他们很可能是不错的员工，只是没有掌握适当的表达方式，不懂如何说服别人，应该鼓励他们找到与队友相处、共事的途径。
3. 有的成员可以应付自己的工作，但他们不爱讨论、分享经验，似乎没有更高的要求。对这类成员，应该让他们与更自信、积极的同事合作，给予他们要求更高的工作，让富有挑战性的工作激发他们的热情。
4. 有的成员在实际工作中显示出较差的技能，不怎么胜任工作。对这类成员，要考虑安排他们做得来的事，调整其在团队中的位置，做到人尽其用；如果的确不适合团队，那就要有壮士断腕的决心。 长期处于磨合阶段的团队，自信心会下降，会出现久病乱投医的现象，我们用什么开发方法，这个模式还是那个模式？我们为啥升职提薪比别的团队差……等等。

---

规范阶段 从磨合阶段毕业，进入规范阶段（Norming）的团队，成员们意识到光争吵是没有用的，大家还是要协同作战。成员们就很多事情取得了一致。角色和职责定义得非常清楚。团队还进行过有趣的团队建设活动。这一时期的团队有如下特点。

1. 团队公开地讨论流程和工作的方式。团队的领导得到广泛的尊重，有能力的成员也分担了一定的领导职责，并自然地获得大家的尊重。
2. 随着项目的开展和成员们的互动，一些成文或不成文的规则逐步建立起来了。
3. 作为一个整体，团队要做什么、不做什么，都更加明确。团队定下了更现实的目标和决心。
4. 通过聆听、讨论，成员互相之间更加了解，认识到并欣赏各自的能力和经验。在工作中互相支持，大家意识到并尊重各人的个性。

在这一阶段，领导主要扮演促成者和鼓励者的角色，协调成员之间的矛盾和竞争关系，建立起流畅的合作模式。要注意到，并不是团队一进入规范阶段，就万事大吉了。经验表明，很多情况下团队会由规范阶段回到磨合阶段，或者在两个阶段间徘徊。团队成员们必须努力工作，才能使团队保持在这一阶段，同时还要抵御外界的压力，以免使团队分裂或回到磨合阶段。另外，一个人要是刚刚加入一个有一定历史的团队，要注意了解这个团队的规范（Norm）是什么，入境随俗。正如西方谚语说——When in Rome, doas the Romans do。

---

创造阶段 经历了萌芽、磨合、规范阶段，现在团队终于可以创造一些有意义的东西——这就是创造阶段（Per-forming）。当然并不是所有的团队都能到达这一阶段。这一阶段的现象如下。 团队知道为何而战，并将注意力集中到如何创造、实现目标上。共同的远景不再是空话，而是实实在在的阶段性成果。这些成果鼓舞了士气，整个团队成为其他团队羡慕的对象。 高度自治，不再需要领导的时时教诲与介入。不同意见仍会出现，但是成员都以一种积极的心态和方式来解决。团队成员相互支持，互相依赖并保持各自的灵活性。团队成员之间都比较熟络，同时也互相信任，个人可以放手独立工作。 角色和职责能够根据项目的要求自然地转换，没有人为此担心或发牢骚。在这种情况下，所有人都能把大部分精力花在工作上。团队士气高涨。能够避免冲突，即使发生冲突，也能妥善解决。 这一阶段团队的效率达到了巅峰状态，而领导则要实践“充分的授权”这一原则，委派得力的人员解决问题，并按期检查。其次是要完善团队业绩和个人绩效相结合的考评体系，最大限度地调动团队成员的积极性。同时安排未来的领导者有机会崭露头角。这样的团队有一个特点：他们一般不会关心或者争执“方法论”的问题——我们究竟是瀑布模型，还是改良的螺旋模型，或者超级敏捷型。我们是CMMI2级还是3级。方法论对于他们，就像水对于鱼一样自然。一个实际的例子就是：微软公司很多员工都不知道何为MSF。当然，这时也必须认识到危险所在。优秀团队有时会骄傲自满，团队成员自我感觉太好，过分亲近也可能导致过度利己，不重视与别的团队合作，不重视客户需求等。最近IT行业的故事一再验证了“伟大的公司离破产只有十八个月”这一规律，优秀团队的领导切莫等闲视之。
