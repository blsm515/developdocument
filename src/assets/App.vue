<template>
	<div id="app">
		<div class="toolbar">完全开发手册</div>
		<section>
			<div class="sliderbar">
				<div class="sidebar-header">
					<el-input placeholder="请输入关键词" suffix-icon="el-icon-search"  v-model="value"  @blur="find">
					</el-input>
				</div>

					<div class="sidebar-body">
      <el-scrollbar style="height: 100%">
							<el-menu  class="el-menu-vertical-demo menu" text-color="#000" active-text-color="#000" background-color="#fafafa" @select="handleSelect" ref="menu" default-active="index">
                  <el-menu-item index="summary" class="slider" >
									<span>概述</span>
								</el-menu-item>
								<el-submenu  index="2">
									<template slot="title" class="slider">
										<span >教程</span>
									</template>

									<el-menu-item-group>
										<el-menu-item index="prepare" class="menu-item">准备</el-menu-item>
										<el-menu-item index="quickstart" class="menu-item">快速上手</el-menu-item>
										<el-menu-item index="apiuse" class="menu-item">JS API的加载</el-menu-item>
										<el-menu-item index="puguse" class="menu-item">插件的使用</el-menu-item>
										<el-menu-item index="map" class="menu-item">地图的组成与名词解释</el-menu-item>
										<el-menu-item index="tep" class="menu-item">基础类型</el-menu-item>
										<el-menu-item index="tep" class="menu-item">地图生命周期</el-menu-item>
										<el-menu-item index="tep" class="menu-item">地图状态</el-menu-item>
										<el-menu-item index="tep" class="menu-item">覆盖物/图层管理</el-menu-item>
										<el-menu-item index="tep" class="menu-item">地图的交互与事件</el-menu-item>
										<el-menu-item index="tep" class="menu-item">自定义地图</el-menu-item>
										<el-menu-item index="tep" class="menu-item">点标记</el-menu-item>
										<el-menu-item index="tep" class="menu-item">海量点标记</el-menu-item>
										<el-menu-item index="tep" class="menu-item">矢量图形</el-menu-item>
										<el-menu-item index="tep" class="menu-item">覆盖物群组</el-menu-item>
										<el-menu-item index="tep" class="menu-item">地图控件</el-menu-item>
										<el-menu-item index="tep" class="menu-item">信息窗体和右键菜单</el-menu-item>
										<el-menu-item index="tep" class="menu-item">创建一个自定义图层实例</el-menu-item>
										<el-menu-item index="tep" class="menu-item">地图和覆盖物事件</el-menu-item>
										<el-menu-item index="tep" class="menu-item">DOM和自定义事件</el-menu-item>
										<el-menu-item index="tep" class="menu-item">坐标系转换</el-menu-item>
										<el-menu-item index="tep" class="menu-item">经纬度与像素坐标的互换</el-menu-item>
										<el-menu-item index="tep" class="menu-item">不同坐标系经纬度坐标互转</el-menu-item>
										<el-menu-item index="tep" class="menu-item">距离长度面积</el-menu-item>
										<el-menu-item index="tep" class="menu-item">计算线面关系等</el-menu-item>
										<el-menu-item index="tep" class="menu-item">覆盖物</el-menu-item>
										<el-menu-item index="tep" class="menu-item">简单信息窗体</el-menu-item>
										<el-menu-item index="tep" class="menu-item">海量数据</el-menu-item>
										<el-menu-item index="tep" class="menu-item">行政地理</el-menu-item>
										<el-menu-item index="tep" class="menu-item">其他组件</el-menu-item>
										<el-menu-item index="tep" class="menu-item">鼠标工具插件</el-menu-item>
										<el-menu-item index="tep" class="menu-item">矢量图形编辑工具</el-menu-item>
										<el-menu-item index="tep" class="menu-item">业务图层要素编辑工具</el-menu-item>
										<el-menu-item index="tep" class="menu-item">地理编码</el-menu-item>
										<el-menu-item index="tep" class="menu-item">路线规划</el-menu-item>
										<el-menu-item index="tep" class="menu-item">公交线路站点查询</el-menu-item>
										<el-menu-item index="tep" class="menu-item">搜索能力族JSAPI</el-menu-item>
										<el-menu-item index="tep" class="menu-item">补充</el-menu-item>
									</el-menu-item-group>
								</el-submenu>
								<el-menu-item index="tep" class="slider">
									<span>示例中心</span>
								</el-menu-item>
							</el-menu>
</el-scrollbar>

					</div>

			</div>

			<article>
				<el-scrollbar style="height: 100%">
					<div class="article-head">
						<h1>{{title}}</h1></div>
					<!-- v-html = "html" -->
					<div class="article-body" v-html="html">

					</div>
				</el-scrollbar>
			</article>

		</section>

	</div>
</template>

<script>
	export default {
		name: 'App',
		components: {

		},
		data() {
			return {
        index:"summary",


				data: [{
						key: "summary",
						title: "概述",
						html: "<h2>简介</h2><p>JS API是一套用JavaScript 语言编写的应用程序接口，您可以通过各种API接口向地图添加内容，创建功能丰富、交互性强的地图应用。JS API提供了大量的实用工具和富有特色的插件功能。 本文档适用于熟悉JavaScript 编程和了解面向对象概念的读者。使用者应该对地图产品有一定的了解。</p>"
					},

					{
						key: "prepare",
						title: "准备",
						html: " <h2>准备页面</h2><p>1.在页面添加 JS API 的入口脚本标签，并将其中「您申请的key值」替换为您刚刚申请的 key；</p><div class='code'><div class='code-title'><a>HTML</a></div><code>&lt;script&nbsp;type='text/javascript'&nbsp;src='https://223.100.246.29:9091/SDKService/jssdk/auth?v=2.0&amp;key=您申请的key值'&gt;&lt;/script&gt;</code></div><p>2.添加div标签作为地图容器，同时为该div指定id属性；</p><div class='code'><div class='code-title'><a>HTML</a></div><code>&lt;div&nbsp;id='container'&gt;&lt;/div&gt;</code></div><p>3.为地图容器指定高度、宽度；</p><div class='code'><div class='code-title'><a>HTML</a></div><code>#container&nbsp;{width:300px;&nbsp;height:&nbsp;180px;&nbsp;}</code></div><p>4.进行移动端开发时，请在head内添加viewport设置，以达到最佳的绘制性能；</p><div class='code'><div class='code-title'><a>HTML</a></div><code>&lt;meta&nbsp;name='viewport'&nbsp;content='initial-scale=1.0,&nbsp;user-scalable=no'&gt;</code></div><p>5.在完成如上准备工作之后便可以开始进行开发工作了。</p><div class='code'><div class='code-title'><a>HTML</a></div><code>window.onLoad = function(){<br/>var map = new CMMap.Map('container');<br/>}<br/>var url = 'http://223.100.246.29:9091/SDKService/jssdk/auth?v=2.0&key=您申请的key值&callback=onLoad';<br/>var jsapi = doc.createElement('script');<br/>jsapi.charset = 'utf-8';<br/>jsapi.src = url;<br/>document.head.appendChild(jsapi);</code></div>"
					},
					{
						key: "quickstart",
						title: "快速上手",
						html: "<h2>HELLO,CMMAP</h2> <p>简单创建一个地图只需要一行代码，构造参数中的container为准备阶段添加的地图容器的id：</p><div class='code'><div class='code-title'><a>HTML</a></div><code> var map = new CMMap.Map('container');</code></div><p> 创建的同时可以给地图设置中心点、级别、显示模式、自定义样式等属性：</p><div class='code'><div class='code-title'><a>JavaScript</a></div><code> var map = new CMMap.Map('container', {<br/>zoom:11,//级别<br/>             center: [116.397428, 39.90923],//中心点坐标<br/>             viewMode:'3D'//使用3D视图<br/> });</code></div><h2>图层</h2><p>默认情况下，地图只显示标准底图，如需要叠加别的图层，可以通过map.add方法添加图层：</p><div class='code'><div class='code-title'><a>JavaScript</a></div><code>var map = new CMMap.Map('container', {<br/> resizeEnable: true,<br/> center: [116.397428, 39.90923],<br/> zoom: 13<br/> });<br/> //实时路况图层<br/> var trafficLayer = new CMMap.TileLayer.Traffic({<br/> zIndex: 10<br/> });<br/>  map.add(trafficLayer);//添加图层到地图</code></div><p>也可以在地图初始化的时候通过layers属性为地图设置多个图层：</p><div class='code'><div class='code-title'><a>JavaScript</a></div><code>   var map = new CMMap.Map('container', {<br/>   center: [116.397428, 39.90923],<br/>   layers: [//使用多个图层<br/>   new CMMap.TileLayer.Satellite(),<br/>   new CMMap.TileLayer.RoadNet()<br/>   ],<br/>   zooms: [4,18],//设置地图级别范围<br/>   zoom: 13<br/>    });</code></div><p>地图 JS API 提供了标准、卫星、路网、路况、建筑等多个图层，也提供了把一般的栅格切片图层、图片图层、Canvas图层、Video图层、热力等作为图层的能力。</p><h2>点标记与矢量地图</h2><p>JS API 提供了在地图之上绘制覆盖物的能力，比如点标记 Marker、文本标记 Text、圆点标记 CircleMarker。添加点标记的方法非常简单，比如添加一个默认样式的Marker：</p><div class='code'><div class='code-title'><a>JavaScript</a></div><code>    var marker = new CMMap.Marker({<br/>     position:[116.39, 39.9]//位置<br/>     })<br/>      map.add(marker);//添加到地图<br/></code></div><p>移除的方法如下：</p><div class='code'><div class='code-title'><a>JavaScript</a></div><code> map.remove(marker)</code></div><p>也提供了绘制圆Circle、折线 Polyline、多边形 Polygon矢量图形的能力，比如添加折线:</p><div class='code'><div class='code-title'><a>JavaScript</a></div><code>var lineArr = [<br/>[116.368904, 39.913423],<br/>[116.382122, 39.901176],<br/>[116.387271, 39.912501],<br/>[116.398258, 39.904600]<br/>];<br/>var polyline = new CMMap.Polyline({<br/>path: lineArr, //设置线覆盖物路径<br/>strokeColor: '#3366FF', //线颜色<br/>strokeWeight: 5, //线宽<br/>strokeStyle: 'solid', //线样式<br/>});<br/>map.add(polyline);</code></div><h2>事件功能与信息窗体</h2><p>JS API 提供的Map、点标记、矢量图形的实例均支持事件，鼠标或者触摸操作均会触发相应的事件。我们通过给点标记绑定click事件来简单了解事件系统和信息窗体的基本使用</p><div class='code'><div class='code-title'><a>JavaScript</a></div><code> var infoWindow = new CMMap.InfoWindow({ //创建信息窗体<br/> isCustom: true, //使用自定义窗体<br/> content:'<div>信息窗体</div>', //信息窗体的内容可以是任意html片段 offset: new CMMap.Pixel(16, -45)<br/> });<br/> var onMarkerClick = function(e) {<br/> infoWindow.open(map, e.target.getPosition());//打开信息窗体 //e.target就是被点击的Marker<br/> }<br/> var marker = new CMMap.Marker({<br/> position: [116.481181, 39.989792]<br/> })<br/>map.add(marker);<br/></code></div>	"

					},
          {
          						key: "apiuse",
          						title: "JS API的加载",
          						html: "<p>JS API 支持多种加载方式，可以顺序加载也可以异步加载，同时也可以作为一般脚本资源被 RequireJS 等前端框架加载。</p><h2>顺序同步加载</h2><p>在「准备」篇中我们使用的是基本的顺序同步加载方式，这种方式下，地图初始化的代码要放在 JS API 的脚本标签之后：</p><div class='code'><div class='code-title'><a>HTML</a></div><code> &lt;script&nbsp;src='http://223.100.246.29:9091/SDKService/jssdk/auth?v=2.0&amp;key=您申请的key值'&gt;&lt;/script&gt;&nbsp;<br/> &lt;script&nbsp;type='text/javascript'&gt;&nbsp;<br/> var&nbsp;map&nbsp;=&nbsp;new&nbsp;CMMap.Map('container',&nbsp;{&nbsp;<br/> {center:[117.000923,36.675807],&nbsp;<br/> zoom:11&nbsp;<br/> });<br/> &nbsp;&lt;/script&gt;</code></div><h2>异步加载</h2><p>异步加载指的是为 JS API 指定加载的回调函数，在 JS API 的主体资源加载完毕之后，将自动调用该回调函数。回调函数应该声明在 JS API 入口文件引用之前，异步加载可以减少对其他脚本执行的阻塞，HTTPS 下我们也建议使用异步方式：</p><div class='code'><div class='code-title'><a>HTML</a></div><code> &lt;script&nbsp;type='text/javascript'&gt;&nbsp;<br/> window.init&nbsp;=&nbsp;function(){&nbsp;<br/> var&nbsp;map&nbsp;=&nbsp;new&nbsp;CMMap.Map('container',&nbsp;{&nbsp;<br/> center:[117.000923,36.675807],&nbsp;<br/> zoom:11<br/> &nbsp;});&nbsp;<br/> }&nbsp;<br/> &lt;/script&gt;&nbsp;<br/> &lt;script&nbsp;src='http://223.100.246.29:9091/SDKService/jssdk/auth?v=2.0&amp;key=您申请的key值&amp;callback=init'&gt;&lt;/script&gt;</code></div><p>或者</p><div class='code'><div class='code-title'><a>JavaScript</a></div><code> window.onLoad = function(){<br/> var map = new CMMap.Map('container');<br/> }<br/> var url ='http://223.100.246.29:9091/SDKService/jssdk/auth?v=2.0&key=您申请的key值&callback=onLoad';<br/> var jsapi = doc.createElement('script');<br/> jsapi.charset ='utf-8';<br/> jsapi.src = url;<br/> document.head.appendChild(jsapi);<br/></code></div><h2>使用RequireJS等加载</h2><p>在使用 RequireJS 等前端框架时，JS API 应该被当作一般脚本资源，并使用上述异步方式进行加载，比如</p><div class='code'><div class='code-title'><a>HTML</a></div><code> &lt;!doctype&nbsp;html&gt;<br/> &nbsp;&lt;html&gt;&nbsp;<br/> &lt;head&gt;&nbsp;<br/> &lt;meta&nbsp;charset='utf-8'&gt;&nbsp;<br/> &lt;meta&nbsp;http-equiv='X-UA-Compatible'&nbsp;content='chrome=1'&gt;<br/> &nbsp;&lt;meta&nbsp;name='viewport'&nbsp;content='initial-scale=1.0,&nbsp;user-scalable=no,&nbsp;width=device-width'&gt;&nbsp;<br/> &lt;style&nbsp;type='text/css'&gt;&nbsp;<br/> body,html,#container{&nbsp;<br/> width:&nbsp;100%;&nbsp;<br/> height:&nbsp;100%;&nbsp;<br/> margin:&nbsp;0px&nbsp;<br/> }&nbsp;<br/> &lt;/style&gt;&nbsp;<br/> &lt;title&gt;通过RequireJS加载&lt;/title&gt;&nbsp;<br/> &lt;/head&gt;<br/> &nbsp;&lt;body&gt;&nbsp;<br/> &lt;div&nbsp;id='container'&nbsp;tabindex='0'&gt;&lt;/div&gt;&nbsp;<br/> &lt;scriptsrc='https://webapi.cmmap.com/js/require.js'&nbsp;data-main='./require-init'&gt;&lt;/script&gt;&nbsp;<br/> &lt;/body&gt;&nbsp;<br/> &lt;/html&gt;</code></div><p>require-init.js</p><div class='code'><div class='code-title'><a>JavaScript</a></div><code> require.config({<br/>paths: {<br/>'cmmap':'http://223.100.246.29:9091/SDKService/jssdk/auth?v=2.0&key=您申请的key值&callback=onCMMapLoaded'<br/>　 }　<br/> });<br/> window.onCMMapLoaded = function() {<br/> require(['initCMMap'], function(mapIniter) {<br/> mapIniter.init();<br/> })<br/> }<br/> require(['CMMap'])</code></div><p>require-init.js</p><div class='code'><div class='code-title'><a>JavaScript</a></div><code> define(function() {<br/>var init = function() {<br/>var CMMap = new CMMap.Map('container');<br/>};<br/>return {<br/>init: init<br/>};<br/>});</code></div>"

          					},
                    {
                    						key: "puguse",
                    						title: "插件的使用",
                    						html: "<p>JS API 提供了众多的插件功能，这些功能不会主动随着 JSAPI 主体资源下发，需要引入之后才能使用这些插件的功能。这些功能包括：<br/>服务类，如：POI搜索 PlaceSearch、输入提示 AutoComplete、地图控件，如：缩放工具条ToolBar、比例尺Scale、定位按钮Geolocation等；<br/>矢量图形编辑工具，如折线/多边形编辑器 PolyEditor、圆形编辑器 CircleEditor等；<br/>工具类，如鼠标绘制工具 MouseTool、测距工具 RangingTool等。</p><h2>插件的使用流程</h2><p>使用插件的功能通常需要三个步骤：<br/> 引入插件，支持按需异步加载和同步加载，可同时引入多个插件；<br/> 创建插件实例，非特殊情况需避免重复创建多个实例，复用同一个实例即可；<br/> 调用实例的方法，使用相关功能。</p><h2>插件的引入</h2><p>异步加载插件</p><p>异步加载指的是在 JS API 加载完成之后，在需要使用到某个插件的时候，通过CMMap.plugin方法按需引入插件，在plugin回调之后使用插件功能</p><div class='code'><div class='code-title'><a>HTML</a></div><code>&lt;script&nbsp;type='text/javascript'&nbsp;src='https://webapi.cmmap.com/maps?v=1.4.7&amp;key=您申请的key值'&gt;&lt;/script&gt;<br/>&lt;script&nbsp;type='text/javascript'&nbsp;&gt;&nbsp;<br/>var&nbsp;map&nbsp;=&nbsp;new&nbsp;CMMap.Map('container',{<br/>&nbsp;zoom:12,&nbsp;<br/>center:[116.39,39.9]<br/>&nbsp;});&nbsp;<br/>CMMap.plugin('CMMap.ToolBar',function(){//异步加载插件&nbsp;<br/>var&nbsp;toolbar&nbsp;=&nbsp;new&nbsp;CMMap.ToolBar();&nbsp;<br/>map.addControl(toolbar);&nbsp;<br/>});<br/>&nbsp;&lt;/script&gt;</code></div><p>异步加载多个插件</p><p>CMMap.plugin的第一个参数使用数组即可同时加载引入多个插件。</p><div class='code'><div class='code-title'><a>JavaScript</a></div><code> CMMap.plugin(['CMMap.ToolBar','CMMap.Driving'],function(){//异步同时加载多个插件<br/>var toolbar = new CMMap.ToolBar();<br/>map.addControl(toolbar);<br/>var driving = new CMMap.Driving();//驾车路线规划<br/>driving.search()<br/>});</code></div><p>同步加载插件</p><p>如果希望和 JS API 的主体同步加载某些插件，而不是异步加载，可以在 JS API 的入口地址中添加plugin参数，将需要使用的一个或者多个插件的名称作为参数即可，这种用法在 JS API 加载完毕之后便可直接使用插件功能了。</p><div class='code'><div class='code-title'><a>HTML</a></div><code>&lt;script&nbsp;type='text/javascript'&nbsp;src='https://webapi.CMmap.com/maps?v=1.4.7&amp;key=您申请的key值&amp;plugin=CMMap.ToolBar'&gt;&lt;/script&gt;&nbsp;<br/>&lt;script&nbsp;type='text/javascript'&nbsp;&gt;&nbsp;<br/>var&nbsp;map&nbsp;=&nbsp;newCMMap.Map('mapContainer',{&nbsp;<br/>zoom:12,&nbsp;<br/>center:[116.39,39.9]<br/>&nbsp;});&nbsp;<br/>var&nbsp;toolbar&nbsp;=&nbsp;newCMMap.ToolBar();&nbsp;<br/>map.plugin(toolbar);<br/>&nbsp;&lt;/script&gt;</code></div><p>同步加载多个插件</p><p>需要加载多个插件时，plugin参数中的插件名称之间以逗号分割。</p><div class='code'><div class='code-title'><a>HTML</a></div><code>&lt;script&nbsp;type='text/javascript'&nbsp;src='https://webapi.cmmap.com/maps?v=1.4.7&amp;key=您申请的key值&amp;plugin=CMMap.ToolBar,CMMap.Driving'&gt;&lt;/script&gt;&nbsp;<br/>&lt;script&nbsp;type='text/javascript'&nbsp;&gt;&nbsp;<br/>var&nbsp;map&nbsp;=&nbsp;new&nbsp;CMMap.Map('mapContainer',{&nbsp;<br/>zoom:12,&nbsp;<br/>center:[116.39,39.9]&nbsp;<br/>});&nbsp;<br/>var&nbsp;toolbar&nbsp;=&nbsp;new&nbsp;CMMap.ToolBar();&nbsp;<br/>map.plugin(toolbar);&nbsp;<br/>var&nbsp;driving&nbsp;=&nbsp;new&nbsp;CMMap.Driving();<br/>&nbsp;driving.search()&nbsp;<br/>&lt;/script&gt;<br/></code></div><h2>插件列表</h2><p>CMMap.Geolocation</p><table class='md-table' style='box-sizing: border-box; font-size:14px;width:100%; font-family: &quot;Helvetica Neue&quot;, Helvetica, &quot;PingFang SC&quot;, &quot;Hiragino Sans GB&quot;, &quot;Microsoft YaHei&quot;, 微软雅黑, Arial, sans-serif; border-collapse: collapse; border-spacing: 0px; margin-bottom: 20px; font-size: 14px; color: rgb(102, 104, 103); margin-top: 0px; line-height: 2; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: 400; letter-spacing: normal; text-align: start; text-indent: 0px; text-transform: none; white-space: normal; word-spacing: 0px; -webkit-text-stroke-width: 0px; background-color: rgb(254, 254, 254); text-decoration-style: initial; text-decoration-color: initial; border-left: 1px solid rgb(222, 222, 222); border-top: 1px solid rgb(222, 222, 222);' width='-814' align='center'><tbody><tr><th> 类名</th><th> 类功能说明</th></tr><tr><td> &nbsp;CMMap.ElasticMarker</td><td>&nbsp;灵活点标记，可以随着地图级别改变样式和大小的 Marker</td></tr><tr><td> &nbsp;CMMap.ToolBar</td><td>&nbsp;工具条，控制地图的缩放、平移等</td></tr><tr><td> &nbsp;CMMap.Scale</td><td> &nbsp;比例尺，显示当前地图中心的比例尺</td></tr><tr><td> &nbsp;CMMap.OverView</td><td>&nbsp;鹰眼，显示缩略图</td></tr><tr><td> &nbsp;CMMap.MapType</td><td> &nbsp;图层切换，用于几个常用图层切换显示</td></tr><tr><td> &nbsp;定位，提供了获取用户当前准确位置、所在城市的方法</td><td><br></td></tr><tr><td colspan='1' rowspan='1'>CMMap.AdvancedInfoWindow</td><td colspan='1' rowspan='1'>高级信息窗体，整合了周边搜索、路线规划功能</td></tr><tr><td> &nbsp;CMMap.Autocomplete</td><td> &nbsp;输入提示，提供了根据关键字获得提示信息的功能</td></div><p>异步加载多个插件</p><p>CMMap.plugin的第一个参数使用数组即可同时加载引入多个插件。</p><div class='code'><div class='code-title'><a>JavaScript</a></div><code> CMMap.plugin(['CMMap.ToolBar','CMMap.Driving'],function(){//异步同时加载多个插件<br/>var toolbar = new CMMap.ToolBar();<br/>map.addControl(toolbar);<br/>var driving = new CMMap.Driving();//驾车路线规划<br/>driving.search()<br/>});</code></div><p>同步加载插件</p><p>如果希望和 JS API 的主体同步加载某些插件，而不是异步加载，可以在 JS API 的入口地址中添加plugin参数，将需要使用的一个或者多个插件的名称作为参数即可，这种用法在 JS API 加载完毕之后便可直接使用插件功能了。</p><div class='code'><div class='code-title'><a>HTML</a></div><code>&lt;script&nbsp;type='text/javascript'&nbsp;src='https://webapi.CMmap.com/maps?v=1.4.7&amp;key=您申请的key值&amp;plugin=CMMap.ToolBar'&gt;&lt;/script&gt;&nbsp;&lt;script&nbsp;type='text/javascript'&nbsp;&gt;&nbsp;var&nbsp;map&nbsp;=&nbsp;newCMMap.Map('mapContainer',{&nbsp;zoom:12,&nbsp;center:[116.39,39.9]&nbsp;});&nbsp;var&nbsp;toolbar&nbsp;=&nbsp;newCMMap.ToolBar();&nbsp;map.plugin(toolbar);&nbsp;&lt;/script&gt;</code></div><p>同步加载多个插件</p><p>需要加载多个插件时，plugin参数中的插件名称之间以逗号分割。</p><div class='code'><div class='code-title'><a>HTML</a></div><code>&lt;script&nbsp;type='text/javascript'&nbsp;src='https://webapi.cmmap.com/maps?v=1.4.7&amp;key=您申请的key值&amp;plugin=CMMap.ToolBar,CMMap.Driving'&gt;&lt;/script&gt;&nbsp;&lt;script&nbsp;type='text/javascript'&nbsp;&gt;&nbsp;var&nbsp;map&nbsp;=&nbsp;new&nbsp;CMMap.Map('mapContainer',{&nbsp;zoom:12,&nbsp;center:[116.39,39.9]&nbsp;});&nbsp;var&nbsp;toolbar&nbsp;=&nbsp;new&nbsp;CMMap.ToolBar();&nbsp;map.plugin(toolbar);&nbsp;var&nbsp;driving&nbsp;=&nbsp;new&nbsp;CMMap.Driving();&nbsp;driving.search()&nbsp;&lt;/script&gt;</code></div><h2>插件列表</h2><p>CMMap.Geolocation</p><table class='md-table' style='box-sizing: border-box; font-size:14px;width:100%; font-family: &quot;Helvetica Neue&quot;, Helvetica, &quot;PingFang SC&quot;, &quot;Hiragino Sans GB&quot;, &quot;Microsoft YaHei&quot;, 微软雅黑, Arial, sans-serif; border-collapse: collapse; border-spacing: 0px; margin-bottom: 20px; font-size: 14px; color: rgb(102, 104, 103); margin-top: 0px; line-height: 2; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: 400; letter-spacing: normal; text-align: start; text-indent: 0px; text-transform: none; white-space: normal; word-spacing: 0px; -webkit-text-stroke-width: 0px; background-color: rgb(254, 254, 254); text-decoration-style: initial; text-decoration-color: initial; border-left: 1px solid rgb(222, 222, 222); border-top: 1px solid rgb(222, 222, 222);' width='-814' align='center'><tbody><tr><th> 类名</th><th> 类功能说明</th></tr><tr><td> &nbsp;CMMap.ElasticMarker</td><td>&nbsp;灵活点标记，可以随着地图级别改变样式和大小的 Marker</td></tr><tr><td> &nbsp;CMMap.ToolBar</td><td>&nbsp;工具条，控制地图的缩放、平移等</td></tr><tr><td> &nbsp;CMMap.Scale</td><td> &nbsp;比例尺，显示当前地图中心的比例尺</td></tr><tr><td> &nbsp;CMMap.OverView</td><td>&nbsp;鹰眼，显示缩略图</td></tr><tr><td> &nbsp;CMMap.MapType</td><td> &nbsp;图层切换，用于几个常用图层切换显示</td></tr><tr><td> &nbsp;定位，提供了获取用户当前准确位置、所在城市的方法</td><td><br></td></tr><tr><td colspan='1' rowspan='1'>CMMap.AdvancedInfoWindow</td><td colspan='1' rowspan='1'>高级信息窗体，整合了周边搜索、路线规划功能</td></tr><tr><td> &nbsp;CMMap.Autocomplete</td><td> &nbsp;输入提示，提供了根据关键字获得提示信息的功能</td></tr><tr><td colspan='1' rowspan='1'>CMMap.PlaceSearch</td><td colspan='1' rowspan='1'>地点搜索服务，提供了关键字搜索、周边搜索、范围内搜索等功能</td></tr><tr><td colspan='1' rowspan='1'>CMMap.PlaceSearchLayer</td><td colspan='1' rowspan='1'>搜索结果图层类，将搜索结果作为图层展示</td></tr><tr><td colspan='1' rowspan='1'>CMMap.DistrictSearch</td><td colspan='1' rowspan='1'>行政区查询服务，提供了根据名称关键字、citycode、adcode 来查询行政区信息的功能</td></tr><tr><td colspan='1' rowspan='1'>CMMap.Geocoder</td><td colspan='1' rowspan='1'>地理编码与逆地理编码服务，提供地址与坐标间的相互转换</td></tr><tr><td colspan='1' rowspan='1'>CMMap.CitySearch</td><td colspan='1' rowspan='1'>城市获取服务，获取用户所在城市信息或根据给定IP参数查询城市信息</td></tr><tr><td colspan='1' rowspan='1'>CMMap.IndoorMap</td><td colspan='1' rowspan='1'>室内地图，用于在地图中显示室内地图</td></tr><tr><td colspan='1' rowspan='1'>CMMap.MouseTool</td><td colspan='1' rowspan='1'>鼠标工具插件</td></tr><tr><td colspan='1' rowspan='1'>CMMap.CircleEditor</td><td colspan='1' rowspan='1'>圆编辑插件</td></tr><tr><td colspan='1' rowspan='1'>CMMap.PolyEditor</td><td colspan='1' rowspan='1'>折线、多边形编辑插件</td></tr><tr><td colspan='1' rowspan='1'>CMMap.RangingTool</td><td colspan='1' rowspan='1'>测距插件，可以用距离或面积测量</td></tr><tr><td colspan='1' rowspan='1'>CMMap.Heatmap</td><td>热力图插件</td></tr></tbody></table>"

                    					},
					{
						key: "map",
						title: "地图的组成与名词解释",
						html: "<h2>JS API地图组成结构</h2><p>使用CMMAP JS API 创建的地图通常由这几部分组成：</p><p>地图容器 Container</p><p>即在准备阶段所创建的指定了id的div对象，这个div将作为承载所有图层、点标记、矢量图形、控件的容器。</p><h3>图层 Layers</h3><p>图层是指能够在视觉上覆盖一定地图范围，用来描述全部或者部分现实世界区域内的地图要素的抽象概念，一幅地图通常由一个或者多个图层组成。如上图中处于整个地图容器最下方的二维矢量图层和实施交通图层.<p>CMMAP JS API 即提供了标准图层、卫星图层、路网图层、路况图层等官方标准图层接口，又提供了加载其他厂商发布的标准地图服务的图层接口，还提供了加载开发者自己的图片、Canvas、视频、热力数据的图层接口。同时也深度开放了可以自定义绘制方法的自定义图层接口。</p><h3>矢量图形 Vector Overlays</h3><p>矢量图形，一般覆盖于底图图层之上，通过矢量的方式(路径或者实际大小)来描述其形状，用几何的方式来展示真实的地图要素，会随着地图缩放而发生视觉大小的变化，但其代表的实际路径或范围不变，如上图中红框内的折线、圆、多边形等。</p><p>除了图中的折线、圆、多边形之外，JS API 还提供了矩形、椭圆、贝瑟尔曲线等常用的矢量图形。</p><h3>点标记 Marker</h3><p>点标记是用来标示某个位置点信息的一种地图要素，覆盖于图层之上。如图中蓝色方框中的两个点状要素。其在屏幕上的位置会随着地图的缩放和中心变化而发生改变，但是会与图层内的要素保持相对静止。</p><p>普通的点标记 (即 Marker ) ,支持将自定义图标和DOM元素作为展示内容。除了 Marker 之外为了满足不同的场景，JS API 另外提供了丰富的点标记类型，比如圆点标记 (CircleMarker) 、文本标记 (Text)、灵活点标记 (ElasticMarker) 。同时我们提供海量点（MassMarks）、点聚合（MarkerCluster）来满足大量点标记的展示需求</p><h3>地图控件 Map Controls</h3><p>控件浮在所有图层和地图要素之上，用于满足一定的交互或提示功能。一般相对于地图容器静止，不随着地图缩放和中心变化而发生位置的变化。</p><h2>JS API地图组成结构</h2><h3>插件 Plugins</h3><p>插件是独立于JS API 地图核心模块之外的一些功能，比如服务类、绘制工具、矢量图形编辑工具、点聚合、热力图等。这些插件不会主动随 JS API的主体资源的加载而下发，使用之前需要提前引入，详见插件的使用。</p><h3>地图级别 ZoomLevel</h3><p>级别与地图的比例尺成正比，每增大一级，地图的比例尺也增大一倍，地图显示的越详细。Web地图的最小级别通常为3级，最大级别各家略有不同，CMMAP JS API 目前最大级别为 17 级。</p><h3>经纬度 LngLat</h3><p>坐标通常指经纬度坐标，CMMAP的坐标范围大致为：东西经180度（-180——180，西半球为负，东半球为正），南北纬85度（-85——85，北半球为正，南半球为负）。</p><h3>底图 BaseLayer</h3><p>严格意义上，底图指处于所有图层和图形最下方的一个图层，通常不透明。可以是单一图层，比如官方标准图层，也可以是图层组合，比图卫星图层和路网图层组合。</p><h3>地图要素 Map Features</h3><p>严格意义的地图要素指的是展示在地图上的地理要素，包括道路、区域面、建筑、POI 标注、路名等。开发者自定义的点标记、矢量图形也可以看做是一种地图要素。</p><h3>标注 Labels</h3><p>我们习惯将底图上自带的标示一定信息的文字或图标称为标注，比如 POI 标注，道路名称标注等。</p><h3>地图平面像素坐标 Plane Coordinates</h3><p>地图平面像素坐标指投影为平面之后的地图上的平面像素坐标，CMMAP使用的Web墨卡托投影，在3级时，平面坐标范围为横纵0-256* 2的3次方 像素，每级别扩大一倍，即第n级的平面坐标范围为 0-256*2 的 n 次方 像素。</p><h3>投影 Projection</h3><p>地图投影指的是将地球球面的经纬度坐标映射到地图平面坐标的变换和映射关系。CMMAP使用 Web 墨卡托投影，即采用 EPSG:3857 坐标系统。</p>"

					},
					{
						key: "tep",
						title: "",
						html: ""

					},
				],
        value:"",
				title: "概述",
				html: "<h2>简介</h2><p>JS API是一套用JavaScript 语言编写的应用程序接口，您可以通过各种API接口向地图添加内容，创建功能丰富、交互性强的地图应用。JS API提供了大量的实用工具和富有特色的插件功能。 本文档适用于熟悉JavaScript 编程和了解面向对象概念的读者。使用者应该对地图产品有一定的了解。</p>"

			}
		},
		mounted() {

		},
		methods: {
			handleSelect(key, keyPath) {
       let cu =  this.data.find((item)=>{
          return item.key ===  key
        })

				this.title = cu.title
				 this.html = cu.html

			},
		find(){
			let cu =  this.data.find((item)=>{
			   return item.title ===  this.value
			 })
       if(cu){
         this.title = cu.title
          this.html = cu.html
          this.index = cu.key
       }else{
         this.title = ""
          this.html = ""
          this.index = ""
       }


		}
		}
	}
</script>

<style>
	body {
		margin: 0 !important;
	}

	#app {
		display: flex;
		flex-direction: column;
		height: 100vh;
		overflow: hidden;
	}

	section {
		/* position: relative;
    top: 56px; */
		display: flex;
		flex: 1;
		min-height: 0;
	}

	.toolbar {
		flex: 0 0 55px;
		height: 55px;
		padding: 0 .8em;
		width: 100%;
		color: #333;
		font-size: 16px;
		line-height: 55px;
		font-weight: 700;
		/* position: fixed; */
		background: #fff;
		border-bottom: 1px solid #ddd;
		z-index: 20;
		top: 0;
	}

	.sliderbar {
		/*  position: fixed; */
		/* top: 57px; */
		/* flex: 0 0 280px; */
		width: 280px;
		bottom: 0;
		/* width: 280px; */
		border-right: 1px solid #ddd;
		background-color: #fafafa;
	}

	.sidebar-header {
		padding: 12px;
		border-bottom: 1px solid #ddd;

	}
	.sidebar-body{
overflow: auto;
    height:668px;
	}

	.slider {
		height: 30px !important;
		line-height: 30px !important;
		font-family: Icons;
		font-style: normal;
		font-weight: 400;
		width: 100%;
	}

	.el-submenu__title {
		height: 30px !important;
		line-height: 30px !important;
	}

	.el-submenu .el-menu-item {
		height: 30px !important;
		line-height: 30px !important;
		padding: 0 45px;
		min-width: 50px !important;
	}

	.el-menu-item-group__title {
		padding: 0;
	}

	article {
		flex: 1;
		width: 0;
		overflow: auto;
		position: relative;
		min-height: 0;
		padding-bottom: 40px;
    height:100%;
	}
	/* .text-main{

      position: absolute;
      top: 0;
      left: 10px;
      padding: 9px 24px;
    } */

	.article-head {
		padding: 10px 20px;
	}

	.article-head h1 {
		margin: 0;
		font-size: 20px;
		font-weight: 200;
		text-align: center;
		line-height: 30px;
		overflow: hidden;
		text-overflow: ellipsis;
		white-space: nowrap;
		color: #7e888b;
	}

	.slider.is-active {
		background-color: #7e888b !important;
	}

	.article-body {
		padding: 9px 24px;
	}

	p {
		line-height: 30px;
		margin: 20px 0;
		font-family: IBM Plex Mono, Space Grotesk, Roboto Slab, Microsoft YaHei, sans-serif;
		font-weight: 300;
		font-size: 17px;
	}

	h2 {
		border-bottom: 1px solid #e7e7e7;
		padding: 10px 0 20px;
		font-size: 24px;
		font-weight: 600;
		font-family: IBM Plex Mono, Space Grotesk, Roboto Slab, sans-serif;
	}

	h3 {
		padding: 10px 0;
		font-size: 20px;
		font-weight: 300;
		font-family: IBM Plex Mono, Space Grotesk, Roboto Slab, sans-serif;
	}

	code {
		display: block;
		font-family: Consolas, Menlo, Courier, monospace!important;
		font-size: 13px;
		background-color: rgb(247, 247, 247);
		line-height: 1.8;
		padding: 6.5px;
	}

	.code {
		border: 1px solid #e7e7e7;
		padding-top: 8px;
	}

	.code-title {
		border-bottom: 1px solid #e7e7e7;
	}

	.code-title a {
		color: #42a5f5;
		border-bottom: 2px solid #42a5f5;
		padding: 0 22px;
		height: 32px;
		line-height: 32px;
		text-decoration: none;
		display: table-cell;
		text-align: center;
		font-size: 14px;
	}

	.el-icon-arrow-down:before {
		content: "^";
	}

	td {
		box-sizing: border-box;
		font-size: 14px;
		font-family: IBM Plex Mono, Space Grotesk, Roboto Slab, sans-serif;
		border: 1px solid rgb(222, 222, 222);
		word-break: break-all;
		text-align: left;
		white-space: nowrap;
		padding: 5px;
		background-color: #fff;
	}

	th {
		box-sizing: border-box;
		font-size: 14px;
		font-family: IBM Plex Mono, Space Grotesk, Roboto Slab, sans-serif;
		border: 1px solid rgb(222, 222, 222);
		word-break: break-all;
		text-align: left;
		white-space: nowrap;
		padding: 5px;
		background-color: rgb(250, 250, 250);
	}

	tr {
		box-sizing: border-box;
		font-size: 14px;
		font-family: IBM Plex Mono, Space Grotesk, Roboto Slab, sans-serif;
		padding: 6px 8px;
		border: 1px solid rgb(217, 219, 219);
		word-break: break-all;
		color: rgb(51, 51, 51);
		background-color: rgb(250, 250, 250);
		text-align: left;
		white-space: nowrap;
	}

	md-table {
		width: 100%;
		border-collapse: collapse;
	}
</style>
