# HTML & CSS

## HTML

- Doctype作用？标准模式与兼容模式各有什么区别?

		（1）、<!DOCTYPE>声明位于位于HTML文档中的第一行，处于 <html> 标签之前。告知浏览器的解析器用什么文档标准解析这个文档。DOCTYPE不存在或格式不正确会导致文档以兼容模式呈现。
		（2）、标准模式的排版 和JS运作模式都是以该浏览器支持的最高标准运行。在兼容模式中，页面以宽松的向后兼容的方式显示,模拟老式浏览器的行为以防止站点无法工作。


- HTML5 为什么只需要写 \<!DOCTYPE HTML\>？

		    HTML5 不基于 SGML，因此不需要对DTD进行引用，但是需要doctype来规范浏览器的行为（让浏览器按照它们应该的方式来运行）；
		
		 而HTML4.01基于SGML,所以需要对DTD进行引用，才能告知浏览器文档所使用的文档类型。

- 行内元素有哪些？块级元素有哪些？ 空(void)元素有那些？

		（1）行内元素有：a b span img input select strong（强调的语气）
		（2）块级元素有：div ul ol li dl dt dd h1 h2 h3 h4…p
		
		（3）常见的空元素：
		        <br> <hr> <img> <input> <link> <meta>

- 页面导入样式时，使用link和@import有什么区别？

		    （1）link属于XHTML标签，除了加载CSS外，还能用于定义RSS, 定义rel连接属性等作用；而@import是CSS提供的，只能用于加载CSS;
		
		（2）页面被加载的时，link会同时被加载，而@import引用的CSS会等到页面被加载完再加载;
		
		（3）import是CSS2.1 提出的，只在IE5以上才能被识别，而link是XHTML标签，无兼容问题;
 

- 介绍一下你对浏览器内核的理解？

		        主要分成两部分：渲染引擎(layout engineer或Rendering Engine)和JS引擎。
		    渲染引擎：负责取得网页的内容（HTML、XML、图像等等）、整理讯息（例如加入CSS等），以及计算网页的显示方式，然后会输出至显示器或打印机。浏览器的内核的不同对于网页的语法解释会有不同，所以渲染的效果也不相同。所有网页浏览器、电子邮件客户端以及其它需要编辑、显示网络内容的应用程序都需要内核。
		
		    JS引擎则：解析和执行javascript来实现网页的动态效果。
		
		    最开始渲染引擎和JS引擎并没有区分的很明确，后来JS引擎越来越独立，内核就倾向于只指渲染引擎。
 

- 常见的浏览器内核有哪些？

		Trident内核：IE,MaxThon,TT,The World,360,搜狗浏览器等。[又称MSHTML]
		        Gecko内核：Netscape6及以上版本，FF,MozillaSuite/SeaMonkey等
		        Presto内核：Opera7及以上。      [Opera内核原为：Presto，现为：Blink;]
		        Webkit内核：Safari,Chrome等。   [ Chrome的：Blink（WebKit的分支）]
 

- html5有哪些新特性、移除了那些元素？如何处理HTML5新标签的浏览器兼容问题？如何区分 HTML 和HTML5？

		    * HTML5 现在已经不是 SGML 的子集，主要是关于图像，位置，存储，多任务等功能的增加。
		          绘画 canvas;
		          用于媒介回放的 video 和 audio 元素;
		          本地离线存储 localStorage 长期存储数据，浏览器关闭后数据不丢失;
		          sessionStorage 的数据在浏览器关闭后自动删除;
		          语意化更好的内容元素，比如 article、footer、header、nav、section;
		          表单控件，calendar、date、time、email、url、search;
		          新的技术webworker, websocket, Geolocation;
		
		      移除的元素：
		          纯表现的元素：basefont，big，center，font, s，strike，tt，u;
		          对可用性产生负面影响的元素：frame，frameset，noframes；
		
		    * 支持HTML5新标签：
		         IE8/IE7/IE6支持通过document.createElement方法产生的标签，
		         可以利用这一特性让这些浏览器支持HTML5新标签，
		         浏览器支持新标签后，还需要添加标签默认的样式。
		
		         当然也可以直接使用成熟的框架、比如html5shim;
		         <!--[if lt IE 9]>
		            <script> src="http://html5shim.googlecode.com/svn/trunk/html5.js"</script>
		         <![endif]-->
		
		    * 如何区分HTML5： DOCTYPE声明\新增的结构元素\功能元素
 
 

- 简述一下你对HTML语义化的理解？

		    用正确的标签做正确的事情。
		    html语义化让页面的内容结构化，结构更清晰，便于对浏览器、搜索引擎解析;
		    即使在没有样式CSS情况下也以一种文档格式显示，并且是容易阅读的;
		    搜索引擎的爬虫也依赖于HTML标记来确定上下文和各个关键字的权重，利于SEO;
		    使阅读源代码的人对网站更容易将网站分块，便于阅读维护理解。
 

- HTML5的离线储存怎么使用，工作原理能不能解释一下？

		    在用户没有与因特网连接时，可以正常访问站点或应用，在用户与因特网连接时，更新用户机器上的缓存文件。
		    原理：HTML5的离线存储是基于一个新建的.appcache文件的缓存机制(不是存储技术)，通过这个文件上的解析清单离线存储资源，这些资源就会像cookie一样被存储了下来。之后当网络在处于离线状态下时，浏览器会通过被离线存储的数据进行页面展示。
		
		
		    如何使用：
		    1、页面头部像下面一样加入一个manifest的属性；
		    2、在cache.manifest文件的编写离线存储的资源；
		        CACHE MANIFEST
		        #v0.11
		        CACHE:
		        js/app.js
		        css/style.css
		        NETWORK:
		        resourse/logo.png
		        FALLBACK:
		        / /offline.html
		    3、在离线状态时，操作window.applicationCache进行需求实现。
 

- 浏览器是怎么对HTML5的离线储存资源进行管理和加载的呢？

		    在线的情况下，浏览器发现html头部有manifest属性，它会请求manifest文件，如果是第一次访问app，那么浏览器就会根据manifest文件的内容下载相应的资源并且进行离线存储。如果已经访问过app并且资源已经离线存储了，那么浏览器就会使用离线的资源加载页面，然后浏览器会对比新的manifest文件与旧的manifest文件，如果文件没有发生改变，就不做任何操作，如果文件改变了，那么就会重新下载文件中的资源并进行离线存储。
		    离线的情况下，浏览器就直接使用离线存储的资源。

- **请描述一下 cookies，sessionStorage 和 localStorage 的区别？**

		        cookie是网站为了标示用户身份而储存在用户本地终端（Client Side）上的数据（通常经过加密）。
		    cookie数据始终在同源的http请求中携带（即使不需要），记会在浏览器和服务器间来回传递。
		    sessionStorage和localStorage不会自动把数据发给服务器，仅在本地保存。
		
		    存储大小：
		        cookie数据大小不能超过4k。
		        sessionStorage和localStorage 虽然也有存储大小的限制，但比cookie大得多，可以达到5M或更大。
		
		    有期时间：
		        localStorage    存储持久数据，浏览器关闭后数据不丢失除非主动删除数据；
		        sessionStorage  数据在当前浏览器窗口关闭后自动删除。
		        cookie          设置的cookie过期时间之前一直有效，即使窗口或浏览器关闭
 

- iframe有那些缺点？

		        *iframe会阻塞主页面的Onload事件；
		    *搜索引擎的检索程序无法解读这种页面，不利于SEO;
		
		    *iframe和主页面共享连接池，而浏览器对相同域的连接有限制，所以会影响页面的并行加载。
		
		    使用iframe之前需要考虑这两个缺点。如果需要使用iframe，最好是通过javascript
		    动态给iframe添加src属性值，这样可以绕开以上两个问题。
 

- Label的作用是什么？是怎么用的？

		    label标签来定义表单控制间的关系,当用户选择该标签时，浏览器会自动将焦点转到和标签相关的表单控件上。
		
		<label for="Name">Number:</label>
		<input type=“text“name="Name" id="Name"/>
		
		<label>Date:<input type="text" name="B"/></label>
 

- HTML5的form如何关闭自动完成功能？

	给不想要提示的 form 或某个 input 设置为 autocomplete=off。

- 如何实现浏览器内多个标签页之间的通信? (阿里)

		    WebSocket、SharedWorker；
		也可以调用localstorge、cookies等本地存储方式；
		
		localstorge另一个浏览上下文里被添加、修改或删除时，它都会触发一个事件，
		我们通过监听事件，控制它的值来进行页面信息通信；
		注意quirks：Safari 在无痕模式下设置localstorge值时会抛出 QuotaExceededError 的异常；
 

- webSocket如何兼容低浏览器？(阿里)

		        Adobe Flash Socket 、
		    ActiveX HTMLFile (IE) 、
		    基于 multipart 编码发送 XHR 、
		    基于长轮询的 XHR
 

- 页面可见性（Page Visibility API） 可以有哪些用途？

		        通过 visibilityState 的值检测页面当前是否可见，以及打开网页的时间等;
		    在页面被切换到其他后台进程的时候，自动暂停音乐或视频的播放；

- 如何在页面上实现一个圆形的可点击区域？

		        1、HTML: map+area或者svg
		    2、CSS: border-radius
		    3、JS: 纯js实现 需要求一个点在不在圆上简单算法、获取鼠标坐标等等
 

- 实现不使用 border 画出1px高的线，在不同浏览器的标准模式与怪异模式下都能保持一致的效果。

		<div style="height:1px;overflow:hidden;background:red"></div>


- 网页验证码是干嘛的，是为了解决什么安全问题。

	区分用户是计算机还是人的公共全自动程序。可以防止恶意破解密码、刷票、论坛灌水；  
	有效防止黑客对某一个特定注册用户用特定程序暴力破解方式进行不断的登陆尝试。



- title与h1的区别、b与strong的区别、i与em的区别？

		title属性没有明确意义只表示是个标题，H1则表示层次明确的标题，对页面信息的抓取也有很大的影响；
		
		        strong是标明重点内容，有语气加强的含义，使用阅读设备阅读网络时：<strong>会重读，而<B>是展示强调内容。
		
		        i内容展示为斜体，em表示强调的文本；
		
		        Physical Style Elements -- 自然样式标签
		        b, i, u, s, pre
		        Semantic Style Elements -- 语义样式标签
		        strong, em, ins, del, code
		        应该准确使用语义样式标签, 但不能滥用, 如果不能确定时首选使用自然样式标签。

## CSS

- 介绍一下标准的CSS的盒子模型？低版本IE的盒子模型有什么不同的？

		        （1）有两种， IE 盒子模型、W3C 盒子模型；
		    （2）盒模型： 内容(content)、填充(padding)、边界(margin)、 边框(border)；
		    （3）区  别： IE的content部分把 border 和 padding计算了进去;
 

- CSS选择符有哪些？哪些属性可以继承？

		        *   1.id选择器（ # myid）
		        2.类选择器（.myclassname）
		        3.标签选择器（div, h1, p）
		        4.相邻选择器（h1 + p）
		        5.子选择器（ul > li）
		        6.后代选择器（li a）
		        7.通配符选择器（ * ）
		        8.属性选择器（a[rel = "external"]）
		        9.伪类选择器（a:hover, li:nth-child）
		
		    *   可继承的样式： font-size font-family color, UL LI DL DD DT;
		
		    *   不可继承的样式：border padding margin width height ;
 

- CSS优先级算法如何计算？

		        *   优先级就近原则，同权重情况下样式定义最近者为准;
		    *   载入样式以最后载入的定位为准;
		
		    优先级为:
		        同权重: 内联样式表（标签内部）> 嵌入样式表（当前文件中）> 外部样式表（外部文件中）。
		        !important >  id > class > tag
		        important 比 内联优先级高

- CSS3新增伪类有那些？

		        举例：
		        p:first-of-type 选择属于其父元素的首个 <p> 元素的每个 <p> 元素。
		        p:last-of-type  选择属于其父元素的最后 <p> 元素的每个 <p> 元素。
		        p:only-of-type  选择属于其父元素唯一的 <p> 元素的每个 <p> 元素。
		        p:only-child        选择属于其父元素的唯一子元素的每个 <p> 元素。
		        p:nth-child(2)  选择属于其父元素的第二个子元素的每个 <p> 元素。
		
		        :after          在元素之前添加内容,也可以用来做清除浮动。
		        :before         在元素之后添加内容
		        :enabled        
		        :disabled       控制表单控件的禁用状态。
		        :checked        单选框或复选框被选中。

- **如何居中div？**

	*  水平居中：给div设置一个宽度，然后添加margin:0 auto属性
			    div{
			        width:200px;
			        margin:0 auto;
			     }
		*  让绝对定位的div居中
				div {
				    position: absolute;
				    width: 300px;
				    height: 300px;
				    margin: auto;
				    top: 0;
				    left: 0;
				    bottom: 0;
				    right: 0;
				    background-color: pink; /* 方便看效果 */
				}
		*  水平垂直居中一
				确定容器的宽高 宽500 高 300 的层
				设置层的外边距
				
				div {
				    position: relative;     /* 相对定位或绝对定位均可 */
				    width:500px; 
				    height:300px;
				    top: 50%;
				    left: 50%;
				    margin: -150px 0 0 -250px;      /* 外边距为自身宽高的一半 */
				    background-color: pink;     /* 方便看效果 */
				
				 }
		*  水平垂直居中二
				未知容器的宽高，利用 `transform` 属性
				
				div {
				    position: absolute;     /* 相对定位或绝对定位均可 */
				    width:500px; 
				    height:300px;
				    top: 50%;
				    left: 50%;
				    transform: translate(-50%, -50%);
				    background-color: pink;     /* 方便看效果 */
				
				}
		*  水平垂直居中三
				利用 flex 布局
				实际使用时应考虑兼容性
				
				.container {
				    display: flex; 
				    align-items: center;        /* 垂直居中 */
				    justify-content: center;    /* 水平居中 */
				
				}
				.container div {
				    width: 100px;
				    height: 100px;
				    background-color: pink;     /* 方便看效果 */
				}  

- display有哪些值？说明他们的作用。

	-  block         块类型。默认宽度为父元素宽度，可设置宽高，换行显示。
	- none          缺省值。象行内元素类型一样显示。
	- inline        行内元素类型。默认宽度为内容宽度，不可设置宽高，同行显示。
	- inline-block  默认宽度为内容宽度，可以设置宽高，同行显示。  
	- list-item     象块类型元素一样显示，并添加样式列表标记。
	-  table         此元素会作为块级表格来显示。
	- inherit       规定应该从父元素继承 display 属性的值。
	- flex              弹性盒子

- position的值relative和absolute定位原点是？

		        absolute
		            生成绝对定位的元素，相对于值不为 static的第一个父元素进行定位。
		          fixed （老IE不支持）
		            生成绝对定位的元素，相对于浏览器窗口进行定位。
		          relative
		            生成相对定位的元素，相对于其正常位置进行定位。
		          static
		            默认值。没有定位，元素出现在正常的流中（忽略 top, bottom, left, right z-index 声明）。
		          inherit
		            规定从父元素继承 position 属性的值。
 

- 请解释一下CSS3的Flexbox（弹性盒布局模型）,以及适用场景？

		一个用于页面布局的全新CSS3功能，Flexbox可以把列表放在同一个方向（从上到下排列，从左到右），并让列表能延伸到占用可用的空间。
		         较为复杂的布局还可以通过嵌套一个伸缩容器（flex container）来实现。
		         采用Flex布局的元素，称为Flex容器（flex container），简称"容器"。
		         它的所有子元素自动成为容器成员，称为Flex项目（flex item），简称"项目"。
		         常规布局是基于块和内联流方向，而Flex布局是基于flex-flow流可以很方便的用来做局中，能对不同屏幕大小自适应。
		         在布局上有了比以前更加灵活的空间。
		
		         具体：http://www.w3cplus.com/css3/flexbox-basics.html


- 用纯CSS创建一个三角形的原理是什么？

		一个div或者元素的border并不是我们直观意义上的一条有高度的线，而是一个等高梯形或者三角形（宽高为0时）
		
		把上、左、右三条边隐藏掉（颜色设为 transparent）
		        #demo {
		          width: 0;
		          height: 0;
		          border-width: 20px;
		          border-style: solid;
		          border-color: transparent transparent red transparent;
		        }

如何实现的：[http://jingyan.baidu.com/article/08b6a591a3208914a809222f.html][1]


- 一个满屏 品 字布局 如何设计?

		    简单的方式：
		        上面的div宽100%，
		        下面的两个div分别宽50%，
		        然后用float或者inline使其不换行即可
  
- css多列等高如何实现？

	答案来源：[http://www.cnblogs.com/2050/archive/2012/07/31/2616460.html][2]

	- 什么是等高布局?

![][image-1]
图中的页面的主体内容是两列结构，左列是用来导航的，右列是用来显示内容的。我们看到它们有一个共同的边框，中间还有一条分隔线，左右两列的高度都是不固定的。这种情况下就需要两列的高度保持一致了，左边高度增加，右边也跟着增加，右边高度增加，左边同样也要增加，否则就会出现“断层”的效果。在这里，等高布局是为了维护边框线条的完整性，在有些地方则可能是为了维护背景的完整性，达到整体一致不缺失的效果。

**布局方案**  

等高布局有几种不同的方法，但目前为止我认为浏览器兼容最好最简便的应该是padding补偿法。首先把列的padding-bottom设为一个足够大的值，再把列的margin-bottom设一个与前面的padding-bottom的正值相抵消的负值，父容器设置超出隐藏，这样子父容器的高度就还是它里面的列没有设定padding-bottom时的高度，当它里面的任一列高度增加了，则父容器的高度被撑到它里面最高那列的高度，其他比这列矮的列则会用它们的padding-bottom来补偿这部分高度差。因为背景是可以用在padding占用的空间里的，而且边框也是跟随padding变化的，所以就成功的完成了一个障眼法。

![][image-2]

在进行具体操作的时候，padding-bottom的值大小取决于你的项目的实际情况，如果不确定，设大一点也无所谓。

- 经常遇到的浏览器的兼容性有哪些？原因，解决方法是什么，常用hack的技巧 ？

	* png24位的图片在iE6浏览器上出现背景，解决方案是做成PNG8.
		 
			* 浏览器默认的margin和padding不同。解决方案是加一个全局的*{margin:0;padding:0;}来统一。
			
			* IE6双边距bug:块属性标签float后，又有横行的margin情况下，在ie6显示margin比设置的大。
			
			  浮动ie产生的双倍距离 #box{ float:left; width:10px; margin:0 0 0 100px;}
			
			  这种情况之下IE会产生20px的距离，解决方案是在float的标签样式控制中加入 ——_display:inline;将其转化为行内属性。(_这个符号只有ie6会识别)
			
			  渐进识别的方式，从总体中逐渐排除局部。
			
			  首先，巧妙的使用“\9”这一标记，将IE游览器从所有情况中分离出来。
			  接着，再次使用“+”将IE8和IE7、IE6分离开来，这样IE8已经独立识别。
			
			  css
			      .bb{
			          background-color:red;/*所有识别*/
			          background-color:#00deff\9; /*IE6、7、8识别*/
			          +background-color:#a200ff;/*IE6、7识别*/
			          _background-color:#1e0bd1;/*IE6识别*/
			      }
			
			
			*  IE下,可以使用获取常规属性的方法来获取自定义属性,
			   也可以使用getAttribute()获取自定义属性;
			   Firefox下,只能使用getAttribute()获取自定义属性。
			   解决方法:统一通过getAttribute()获取自定义属性。
			
			*  IE下,even对象有x,y属性,但是没有pageX,pageY属性;
			   Firefox下,event对象有pageX,pageY属性,但是没有x,y属性。
			
			*  解决方法：（条件注释）缺点是在IE浏览器下可能会增加额外的HTTP请求数。
			
			*  Chrome 中文界面下默认会将小于 12px 的文本强制按照 12px 显示,
			   可通过加入 CSS 属性 -webkit-text-size-adjust: none; 解决。
			
			超链接访问过后hover样式就不出现了 被点击访问过的超链接样式不在具有hover和active了解决方法是改变CSS属性的排列顺序:
			L-V-H-A :  a:link {} a:visited {} a:hover {} a:active {}

- li与li之间有看不见的空白间隔是什么原因引起的？有什么解决办法？

	行框的排列会受到中间空白（回车\空格）等的影响，因为空格也属于字符,这些空白也会被应用样式，占据空间，所以会有间隔，把字符大小设为0，就没有空格了。

- 为什么要初始化CSS样式。

		    - 因为浏览器的兼容问题，不同浏览器对有些标签的默认值是不同的，如果没对CSS初始化往往会出现浏览器之间的页面显示差异。
		
		    - 当然，初始化样式会对SEO有一定的影响，但鱼和熊掌不可兼得，但力求影响最小的情况下初始化。
		
		    最简单的初始化方法： * {padding: 0; margin: 0;} （强烈不建议）
		
		    淘宝的样式初始化代码：
		    body, h1, h2, h3, h4, h5, h6, hr, p, blockquote, dl, dt, dd, ul, ol, li, pre, form, fieldset, legend, button, input, textarea, th, td { margin:0; padding:0; }
		    body, button, input, select, textarea { font:12px/1.5tahoma, arial, \5b8b\4f53; }
		    h1, h2, h3, h4, h5, h6{ font-size:100%; }
		    address, cite, dfn, em, var { font-style:normal; }
		    code, kbd, pre, samp { font-family:couriernew, courier, monospace; }
		    small{ font-size:12px; }
		    ul, ol { list-style:none; }
		    a { text-decoration:none; }
		    a:hover { text-decoration:underline; }
		    sup { vertical-align:text-top; }
		    sub{ vertical-align:text-bottom; }
		    legend { color:#000; }
		    fieldset, img { border:0; }
		    button, input, select, textarea { font-size:100%; }
		    table { border-collapse:collapse; border-spacing:0; }
 
 

- absolute的containing block(容器块)计算方式跟正常流有什么不同？

		    无论属于哪种，都要先找到其祖先元素中最近的 position 值不为 static 的元素，然后再判断：
		    1、若此元素为 inline 元素，则 containing block 为能够包含这个元素生成的第一个和最后一个 inline box 的 padding box (除 margin, border 外的区域) 的最小矩形；
		    2、否则,则由这个祖先元素的 padding box 构成。
		    如果都找不到，则为 initial containing block。
		
		    补充：
		    1. static(默认的)/relative：简单说就是它的父元素的内容框（即去掉padding的部分）
		    2. absolute: 向上找最近的定位为absolute/relative的元素
		    3. fixed: 它的containing block一律为根元素(html/body)，根元素也是initial containing block

- CSS里的visibility属性有个collapse属性值是干嘛用的？在不同浏览器下以后什么区别？

	其实visibility可以有第三种值，就是collapse。当一个元素的visibility属性被设置成collapse值后，对于一般的元素，它的表现跟hidden是一样的。但例外的是，如果这个元素是table相关的元素，例如table行，table group，table列，table column group，它的表现却跟display: none一样，也就是说，它们占用的空间也会释放。
	 
	各种浏览器对collapse值的处理方式不一样。
		- 在谷歌浏览器里，使用collapse值和使用hidden值没有什么区别。 (See this bug report and comments)
	- 在火狐浏览器、Opera和IE11里，使用collapse值的效果就如它的字面意思：table的行会消失，它的下面一行会补充它的位置。

	display:none与visible:hidden的区别
	display:none和visible:hidden都能把网页上某个元素隐藏起来，但两者有区别:
	 
	display:none ---不为被隐藏的对象保留其物理空间，即该对象在页面上彻底消失，通俗来说就是看不见也摸不到。
	 
	visible:hidden--- 使对象在网页上不可见，但该对象在网页上所占的空间没有改变，通俗来说就是看不见但摸得到。


- position跟display、margin collapse、overflow、float这些特性相互叠加后会怎么样？

	[http://www.cnblogs.com/jackyWHJ/p/3756087.html][3]

- css定义的权重

		    以下是权重的规则：标签的权重为1，class的权重为10，id的权重为100，以下例子是演示各种定义的权重值：
		
		    /*权重为1*/
		    div{
		    }
		    /*权重为10*/
		    .class1{
		    }
		    /*权重为100*/
		    #id1{
		    }
		    /*权重为100+1=101*/
		    #id1 div{
		    }
		    /*权重为10+1=11*/
		    .class1 div{
		    }
		    /*权重为10+10+1=21*/
		    .class1 .class2 div{
		    }
		
		    如果权重相同，则最后定义的样式会起作用，但是应该避免这种情况出现
 

- 请解释一下为什么需要清除浮动？清除浮动的方式

	清除浮动是为了清除使用浮动元素产生的影响。浮动的元素，高度会塌陷，而高度的塌陷使我们页面后面的布局不能正常显示。

		        1、父级div定义height；
		    2、父级div 也一起浮动；
		    3、常规的使用一个class；
		        .clearfix:before, .clearfix:after {
		            content: " ";
		            display: table;
		        }
		        .clearfix:after {
		            clear: both;
		        }
		        .clearfix {
		            *zoom: 1;
		        }
		
		    4、SASS编译的时候，浮动元素的父级div定义伪类:after
		        &:after,&:before{
		            content: " ";
		            visibility: hidden;
		            display: block;
		            height: 0;
		            clear: both;
		        }
		
		    解析原理：
		    1) display:block 使生成的元素以块级元素显示,占满剩余空间;
		    2) height:0 避免生成内容破坏原有布局的高度。
		    3) visibility:hidden 使生成的内容不可见，并允许可能被生成内容盖住的内容可以进行点击和交互;
		    4）通过 content:"."生成内容作为最后一个元素，至于content里面是点还是其他都是可以的，例如oocss里面就有经典的 content:".",有些版本可能content 里面内容为空,一丝冰凉是不推荐这样做的,firefox直到7.0 content:”" 仍然会产生额外的空隙；
		    5）zoom：1 触发IE hasLayout。
		
		    通过分析发现，除了clear：both用来闭合浮动的，其他代码无非都是为了隐藏掉content生成的内容，这也就是其他版本的闭合浮动为什么会有font-size：0，line-height：0。

- 什么是外边距合并？

		外边距合并指的是，当两个垂直外边距相遇时，它们将形成一个外边距。
		    合并后的外边距的高度等于两个发生合并的外边距的高度中的较大者。
		    w3school介绍网址： http://www.w3school.com.cn/css/css_margin_collapsing.asp

- zoom:1的清除浮动原理?

		        清除浮动，触发hasLayout；
		    Zoom属性是IE浏览器的专有属性，它可以设置或检索对象的缩放比例。解决ie下比较奇葩的bug。
		    譬如外边距（margin）的重叠，浮动清除，触发ie的haslayout属性等。
		
		    来龙去脉大概如下：
		    当设置了zoom的值之后，所设置的元素就会就会扩大或者缩小，高度宽度就会重新计算了，这里一旦改变zoom值时其实也会发生重新渲染，运用这个原理，也就解决了ie下子元素浮动时候父元素不随着自动扩大的问题。
		
		    Zoom属是IE浏览器的专有属性，火狐和老版本的webkit核心的浏览器都不支持这个属性。然而，zoom现在已经被逐步标准化，出现在 CSS 3.0 规范草案中。
		
		    目前非ie由于不支持这个属性，它们又是通过什么属性来实现元素的缩放呢？
		    可以通过css3里面的动画属性scale进行缩放。
 

- 移动端的布局用过媒体查询吗？

	 
		假设你现在正用一台显示设备来阅读这篇文章，同时你也想把它投影到屏幕上，或者打印出来，
		而显示设备、屏幕投影和打印等这些媒介都有自己的特点，CSS就是为文档提供在不同媒介上展示的适配方法
		
		<!-- link元素中的CSS媒体查询 -->
		当媒体查询为真时，相关的样式表或样式规则会按照正常的级联规被应用。
		当媒体查询返回假， <link> 标签上带有媒体查询的样式表 仍将被下载 （只不过不会被应用）。
		
		<link rel="stylesheet" media="(max-width: 800px)" href="example.css" />
		
		<!-- 样式表中的CSS媒体查询 -->
		包含了一个媒体类型和至少一个使用 宽度、高度和颜色等媒体属性来限制样式表范围的表达式。
		CSS3加入的媒体查询使得无需修改内容便可以使样式应用于某些特定的设备范围。
		
		<style>
		    @media (min-width: 700px) and (orientation: landscape){
		      .sidebar {
		        display: none;
		      }
		    }
		</style>
 
 
- 使用 CSS 预处理器吗？喜欢那个？
- CSS优化、提高性能的方法有哪些？

				1.关键选择器（key selector）。选择器的最后面的部分为关键选择器（即用来匹配目标元素的部分）；
			如果规则拥有 ID 选择器作为其关键选择器，则不要为规则增加标签。过滤掉无关的规则（这样样式系统就不会浪费时间去匹配它们了）；
			2.提取项目的通用公有样式，增强可复用性，按模块编写组件；增强项目的协同开发性、可维护性和可扩展性;
			使用预处理工具或构建工具（gulp对css进行语法检查、自动补前缀、打包压缩、自动优雅降级）；
	

- 浏览器是怎样解析CSS选择器的？

				样式系统从关键选择器开始匹配，然后左移查找规则选择器的祖先元素。
			只要选择器的子树一直在工作，样式系统就会持续左移，直到和规则匹配，或者是因为不匹配而放弃该规则。
	

- 在网页中的应该使用奇数还是偶数的字体？为什么呢？

			偶数字号相对更容易和 web 设计的其他部分构成比例关系。比如：当我用了 14 px 的正文字号，我可能会在一些地方用 14 × 0.5 = 7 px 的 margin

- margin和padding分别适合什么场景使用？

				margin是用来隔开元素与元素的间距；padding是用来隔开元素与内容的间隔。
			margin用于布局分开元素使元素与元素互不相干；
			padding用于元素与内容之间的间隔，让内容（文字）与（包裹）元素之间有一段
	

- 抽离样式模块怎么写，说出思路，有无实践经验？

			抽离多页面公共项目css用webpack的extract-text-webpack-plugin插件就可以

- 元素竖向的百分比设定是相对于容器的高度吗？

	答案来源[http://blog.csdn.net/oiu1010110/article/details/53191541][4]
		元素竖向的百分比设定是相对于容器的宽度or高度
		相对于父元素宽度的：
		[max/min-]width、left、right、padding、margin 等；
		
		相对于父元素高度的：
		[max/min-]height、top、bottom 等；
		
		相对于继承字号的：
		font-size 等；
		
		相对于自身字号的：
		line-height 等；
		
		相对于自身宽高的：
		border-radius、background-size、transform: translate()、transform-origin、zoom、clip-path 等；
		
		特殊算法的：
		background-position（方向长度 / 该方向除背景图之外部分总长度 * 100）、
		filter 系列函数等；

- 全屏滚动的原理是什么？用到了CSS的那些属性？

			CSS-页面滑屏滚动原理
	
	现在的网站有的时候为了简洁就是很多的单页滑屏滚动介绍，主要呈现方式有两种，一种是整体的元素一直排列下去，假设有五个需要展示的全屏页面，那么高度是500%，只是展示100%，剩下的可以通过transform进行Y轴定位，也可以通过margin-top实现，第二种就是所有的子元素和页面一样，都显示在当前页面，简单的实现第一种页面。	


	http://www.jianshu.com/p/ce0582aaa327
			jQuery思路是：
			1、要得到当前页面的下标。
			2、判断鼠标滚轮式向上滑动还是向下滑动，如果向上滑动，下标减一，反之就是加一。
			3、向下滑动，当前页面高度从100%减到0，类似于display：none的效果，只有当前页面的高度为100%时，其他屏的内容高度均为0，则隐藏；同时当前页面的下一个页面高度从0增加到100%。然后还可以添加个侧边的导航的小点，绑定每个相应的div，这样也可以通过这些点来控制内容的滑动。
- 什么是响应式设计？响应式设计的基本原理是什么？如何兼容低版本的IE？

	作者：屹峰
	链接：https://www.zhihu.com/question/20976405/answer/16781171
	来源：知乎
	著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
	
	起因   
	 因为越来越多的智能移动设备（ mobile, tablet device ）加入到互联网中来，移动互联网不再是独立的小网络了，而是成为了 Internet 的重要组成部分。响应式网络设计 （ RWD / AWD）的出现，目的是为移动设备提供更好的体验，并且整合从桌面到手机的各种屏幕尺寸和分辨率，用技术来使网页适应从小到大（现在到超大）的不同分辨率的屏幕。
	注： Responsive Web Design ＝ RWD，Adaptive Web Design ＝ AWD，下同
	
	设计
	RWD：
	
	- 采用 CSS 的 media query 技术
	- 流体布局（ fluid grids ）
	- 自适应的图片/视频等资源素材（为小、中、大屏幕做一些优化，目的是让任何尺寸的屏幕空间都能得到充分利用）
	AWD：
	
	- CSS media query 技术（仅针对有限几种预设的屏幕尺寸设计）
	- 用 Javascript 来操作 HTML 内容
	- 在服务器端操作 HTML 内容（比如为移动端减少内容，为桌面端提供更多内容）
	
	设计思路
	Mobile First（从移动端开始，RWD ）：
	一切从最小屏幕的手机端开始（比如 iPhone 的 320px ），先确定内容，然后逐级往大屏幕设计。
	不同于原来网页设计，总是从桌面电脑的 1024px 开始的。

	如何兼容IE？
	作者：妞妞
	链接：https://www.zhihu.com/question/21634225/answer/35194052
	来源：知乎
	著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
	
	Internet Explorer 8 和 9Internet Explorer 8 和 9 是被支持的，然而，你要知道，很多CSS3属性和HTML5元素 -- 例如，圆角矩形和投影 -- 是肯定不被支持的。另外，Internet Explorer 8 需要Respond.js配合才能实现对媒体查询（media query）的支持。Internet Explorer 8 和 Respond.js在开发环境和生产（线上）环境需要支持 Internet Explorer 8 时，请务必注意下面给出的警告。Respond.js 和 跨域（cross-domain） CSS 的问题如果 Respond.js 和 CSS 文件被放在不同的域名或子域名下面（例如，使用CDN）时需要一些额外的设置。请参考 Respond.js 文档 获取详细信息。Respond.js 和 file://由于浏览器的安全规则问题，Respond.js 不能通过 file:// 协议（打开本地HTML文件所用的协议）访问的页面上发挥正常的功能。如果需要测试IE8下面的响应式特性，必须用http服务器（例如apache、nginx）托管HTML页面才可以。请参考 Respond.js 文档 获取更多信息。Respond.js 和@importRespond.js 不支持通过 @import 引入的CSS文件。例如，Drupal 一般被配置为通过 @import 引入CSS文件，Respond.js对其将无法起到作用。 请参考Respond.js 文档获取更多信息。Internet Explorer 8 与 box-sizingIE8不能完全支持box-sizing: border-box;与min-width、max-width、min-height或max-height一同使用。由于此原因，从Bootstrap v3.0.1版本开始，我们不再为.container使用max-width。IE兼容模式Bootstrap不支持IE的兼容模式。为了让IE浏览器运行最新的渲染模式，建议将此 <meta> 标签加入到你的页面中：<meta http-equiv="X-UA-Compatible" content="IE=edge">此标签被加入到所有文档页面和案例页面中，以确保在每个被支持的IE浏览器中保持最好的页面展现效果。参见StackOverflow上对此问题的解答。

- 视差滚动效果，如何给每页做不同的动画？（回到顶部，向下滑动要再次出现，和只出现一次分别怎么做？）

	??  使用skrollr

- 清除浮动的常用方式总结

	/*------总结：常用的清除浮动的方法。
	1、使用空标签清除浮动。我用了很久的一种方法，空标签可以是div标签，也可以是P标签。我习惯用<P>，够简短，也有很多人用<hr>，只是需要另外 为其清除边框，但理论上可以是任何标签。这种方式是在需要清除浮动的父级元素内部的所有浮动元素后添加这样一个标签清除浮动，并为其定义CSS代 码：clear:both。此方法的弊端在于增加了无意义的结构元素。
	
	对于使用额外标签清除浮动（闭合浮动元素），是W3C推荐的 做法。至于使用<br />元素还是空<div></div>可以根据自己的喜好来选（当然你也可以使用其它块级元素）。不过要注意的 是，<br />本身是有表现的，它会多出一个换行出来，所以要设定它的heigh为0，以隐藏它的表现。所以大多数情况下使用空<div>比较合 适。
	
	2、使用overflow属性。此方法有效地解决了通过空标签元素清除浮动而不得不增加无意代码的弊端。使用该方法是只需在需要清除浮动的元素中定义CSS属性：overflow:auto，即可！”zoom:1″用于兼容IE6,也可以用width:100%。
	
	不过使用overflow的时候，可能会对页面表现带来影响，而且这种影响是不确定的，你最好是能在多个浏览器上测试你的页面；
	
	3、使用after伪对象清除浮动。 该方法只适用于非IE浏览器 。具体写法可参照以下示例。使用中需注意以下几点。一、该方法中必须为需要清除浮动元素的伪对象中设置height:0，否则该元素会比实际高出若干像 素；二、content属性是必须的，但其值可以为空，蓝色理想讨论该方法的时候content属性的值设为”.”，但我发现为空亦是可以的。
	
	此三种方法各有利弊，使用时应择优选择，个人习惯于第一种，比较稳定可靠。
	参考链接：http://www.cnblogs.com/fengzheng126/archive/2012/05/19/2508778.html
	------*/

[1]:	http://jingyan.baidu.com/article/08b6a591a3208914a809222f.html
[2]:	http://www.cnblogs.com/2050/archive/2012/07/31/2616460.html
[3]:	http://www.cnblogs.com/jackyWHJ/p/3756087.html
[4]:	http://blog.csdn.net/oiu1010110/article/details/53191541

[image-1]:	1.png
[image-2]:	2.png