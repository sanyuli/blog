![Rework](/images/rework.jpg)

今天是五一劳动节，算算自己也在企业应用的开发上面也将近摸索了将近五年。从一开始的 java、c 开发到2年前开始专注于前端；
从一开始对个别技术的盲目崇拜到现在更重视针对不同场景进行抉择；从一开始只会在 Eclipse 菜单里面乱找，连快捷键都记不
住几个的菜鸟到现在习惯vim的各种配置（不贬低IDE对于编译语言的巨大贡献，只想说只有 vim 这种灵活的编辑器才能让程序员把
编码技巧提升到极限）。时过境迁，现在想起当年认为 java 是编程语言的王者，windows 是最好用的操作系统就觉得真是可笑。

最近在读《Rework》这本书，有感于别人先进的经验，再对比公司落后低效的管理、 开发方式和日新月异的互联网技术发展，
我觉得是时候对我们的企业应用开发好好思考一下了。本文就来比较下现在的技术环境和数年之前有何不同。

##脚本语言

服务端的脚本语言大幅度提高了开发效率。你或许会这样想，我用java/C#在IDE里面有智能提示等等一大堆辅助工具，开发效率
很高，使用脚本时API只能在网上慢慢找。确实，IDE对于脚本的支持虽说有所进步，但很难与编译语言相提并论，但这真的是问题所
在吗？就拿node来说，做应用开发常用的底层API总共就那么几十个（没有方式重载、接口以及令人头晕目旋的复杂继承关系），很
容易理解记忆，再加上编辑器的自动完成之类的简单辅助，开发效率不比你用IDE慢多少。还有人会说，脚本不过是节省了编译时间
而已，整体上脚本代码可读性很差，难以维护。好吧，如果你对脚本语言的认识还停留在复制粘帖他人网站上的代码片段，你大概是
无法体会到脚本语言的架构之美了，或许你一下无法理解Sencha框架的精妙之处，不过我建议你可以看看Connect、mocha、jade这些
在node社区中被广为使用的代码库（至少我是被它们的简洁优美所折服了）。脚本语言无需编译只是一个表面，再说现在机器性能都
高了， 就算编译 一般也不用了多久，更别提性能上的优势了。其实脚本的真正优势在于脚本的动态性可以让代码更加的精炼，原来
需要数十行的任务现在两三行代码就能搞定了，原来需要的各种xml的配置，复杂类关系设计设计现在也不那么需要了，取而代之的是
在开源的仓库中寻找别人做好的模块，花点时间学习便能用于自己项目之中。换言之，代码的精简和语义化程度的提高使得开发者
阅读、修改代码的成本被极大的降低了，而这个成本相比起初的开发成本往往要高出数倍！如果你要说你只管开发项目，不考虑维护，
那我只能祝你好运了。

##开源

开源的力量波涛汹涌，已经深入到了软件开发的方方面面。我们有开源的优秀操作系统Linux来提供高效、稳定的服务；我们有开源的
技术标准html5、ECMAScript，而且已被各种浏览器所广泛支持，通过开源的互联网技术标准，我们可以让代码实现编写一次，处处运行;
我们有蒸蒸日上开源框架jQuery、Bootstrap等等；我们有不断壮大发展的开源社区node、component等等。开源的资源在互联网上唾手
可得，对开发者来说，不仅仅是能直接学习到大师的杰作， 也不仅仅是可以亲自参与到伟大的项目中做出自己的贡献，更重要的是
我们无需从语言底层开始构建自己的类库，而是找到别人业已完善、足够成熟的库拿来使用。没必要再投入过多的研发和维护精力用到
底层研究，花更多时间做好你的产品，完善你的服务吧。


##版本控制

现代化的版本控制工具已经不再是那个让人爱恨交加，经常各种问题（冲突、服务器错误），甚至发生数据损坏(服务器硬盘损坏)的中央
式管理工具了。以git为例，我们不仅可以随意的创建切换分支，更可以享受随时随地的办公，我们可以本地提交，而且整个项目的记录
完全保存在本地，查看提交记录和差异比较毫秒间就可以完成。另外只需要校验sha1值你就可以轻松保证代码的完整一致，哪怕它已存在数
年，甚至数十年。

##数据库

传统的关系数据库几十年前就有了，nosql的崛起还是近两年的事。传统的关系数据库以健壮、稳定而著称，但是在可扩展性、查询性
能等方面先天不足，所以面对汹涌而来的海量数据时代显得力不从心也就情有可原了。这里不谈nosql数据库对于海量数据处理的强势之处，
因为企业内应用极少碰到海量数据的情况，我们来看看它对我们开发带来的益处。首先，不必再殚精竭虑设计库表结构了（注意，如果你的开
发者未经训练或者极少沟通请略过此条），你可以随意的改变文档的结构而不必受限于各种唯一性、原子性的限制之中各种左右为 难，尽管
有时这样的能力也是有代价的，但它给开发带来的便利不容小觑；其次，忘掉那些该死的约束和事务吧，如果你的应用不是用户转帐之
类的需要回滚操作，你压根就不需要什么事务，看看那些所谓java注解给你代码可读性造成的严重破坏吧（Ruby on rails的解决方案好不少，
不过太多元编程加重了语言本身的学习、维护负担），我不相信有人喜欢他们；最后，面向文档的API比sql的可读性和可编程性要高出许多，
尽管sql已作为标准而被广泛支持，但是没人喜欢拼接字符串，我知道你会选择一个ORM，不过我也肯定你不会喜欢整天在一堆配置文件和源
代码之间纠结。

##移动设备

现在的移动开发基本上被Java（Android）和Object-C（ios）所垄断着，不过终有一天大部分应用都会被html5的应用取而代之。
原因很简单，一方面html5在浏览器支持上已经不是太大问题，更重要的是成本优势，雇佣多个使用不同开发语言的开发者来维护多个不同
版本可一点都不划算。 你可能要质疑html5还不成熟，就连互联网巨头Facebook都放弃了，可事实上根源是Facebook急于求成，他们并没有
找到最合适的解决方案（也可能是被低端的移动设备所限制了），不信可以去看看Sencha出的Fastbook应用。互联网巨头应用的问题都集中
在超大数据量（动辄上亿）对于应用的挑战，所以要采取一些极端的方案来解决这样的问题，好在我们的中小企业应用碰不到这类问题，
性能问题通常稍作优化即可。

其实移动应用的开发最大的难题在于设计，包括界面和交互。为了是让你的应用在小屏幕上有个舒服的布局，并且可以用手势更加方便的操作，
现在已经出现了多种设计方式。一种是所谓的响应式设计，通常采用Media Queries、fluid grid等技术，这种方式用来解决展示型页面的布局
问题简单有效，还有一种就是后端判断请求来源返回不同页面，对与相对复杂的流程应用这种方案更为理想，因为一来可以为移动端用户提供更为
优质的操作体验，二来代码可以更好的模块化，将来升级也会容易的多。

##云服务

我觉得终有一天云服务会抢走绝大多数IT运维人员的饭碗，不过要想让中小企业用上云还是要解决不少问题：

1. 不了解、不信任，因为云服务现在还处于早期，国人又普遍缺乏安全感。不过随着云的普及和人们认识的深入，这方面一定会改善许多。
2. 网络限制，如果你把客户端做的很臃肿，放在局域网没什么问题，不过到了互联网上面，网速不给力的话就会严重影响到用户的体验了，
所以建议尽量选用轻量级的前端框架。
3. 安全。许多习惯了局域网的企业应用基本上可以说豪无安全可言，这样的应用放到互联网上只会成为别人的靶子，被他人利用，最后给客户
造成难以挽回的损失。所以如果想为客户提供可靠的云端服务，请把安全做为重中之重。

- - - 
其实《Rework》所讲的都是管理上的创新，不过之所以他们能在管理上有所创新，根源还是在于技术的进步。
最后，向勇于创新、乐于分享的开源工作者致以最崇高的敬意，你们是这个社会发展改良的源动力。

_(完)_