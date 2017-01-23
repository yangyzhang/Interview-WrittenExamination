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

	  block       	块类型。默认宽度为父元素宽度，可设置宽高，换行显示。  
	  none        	缺省值。象行内元素类型一样显示。
	  inline      	行内元素类型。默认宽度为内容宽度，不可设置宽高，同行显示。
	  inline-block  默认宽度为内容宽度，可以设置宽高，同行显示。
	  list-item   	象块类型元素一样显示，并添加样式列表标记。
	  table       	此元素会作为块级表格来显示。
	  inherit     	规定应该从父元素继承 display 属性的值。

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


