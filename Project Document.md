[toc]
# 一、项目环境搭建
## 1.1 uniapp简介

[官网](https://uniapp.dcloud.io/README)

uni-app 是一个使用 Vue.js 开发所有前端应用的框架，开发者编写一套代码，可发布到iOS、Android、Web（响应式）、以及各种小程序（微信/支付宝/百度/头条/飞书/QQ/快手/钉钉/淘宝）、快应用等多个平台。

## 1.2 HbuilderX
[hbuilderX官网](https://www.dcloud.io/hbuilderx.html)

uniapp开发建议使用HbuilderX工具，因为它的使用更方便，插件更丰富。
![1.png](https://note.youdao.com/yws/res/6142/WEBRESOURCE53523f9ca349be14aea0a916c33cb660)

我们选择对应的版本下载安装即可
![2.png](https://note.youdao.com/yws/res/6073/WEBRESOURCE1ce8c575bb0b872781a96111f278221d)

安装的时候注意：
1. 安装所在的目录必须是英文目录不能有中文或者其他特殊的符号
2. 压缩包直接压缩即可，不用安装
3. 找到exe应用程序发送到桌面快捷方式

## 1.3创建项目

### （1）创建项目
打开HbuilderX编辑器，操作如下，创建一个uniapp项目。
![1.png](https://note.youdao.com/yws/res/6085/WEBRESOURCE5b1e988bab2b0dfb7c2895bf950982ec)

创建好的项目目录如下：
![2.png](https://note.youdao.com/yws/res/6146/WEBRESOURCE827321cfaaaf7b77d85f5cf6b62ab340)

### （2）配置manifest.json
![2.png](https://note.youdao.com/yws/res/6065/WEBRESOURCEe0319ca0ce3c28e2b774a34890762d47)

### （3）配置运行配置

打开HbuilderX开发者工具，操作如下：

![3.png](https://note.youdao.com/yws/res/6070/WEBRESOURCE4dee6b216753ea806a0b790b2611af80)

### （4）打开微信开发者工具的服务端

打开微信开发者工具，打开设置--安全设置--打开服务端口

![1.png](https://note.youdao.com/yws/res/6083/WEBRESOURCE6f6ecd96d392e5f953f1363f1aa36f97)

### （5）安装sass插件

因为uniapp项目使用的是sass语法，所以你第一次打开的时候会提示你安装sass插件，你自己按照提示安装即可。注意安装好重启Hbuilderx编辑器。

### （6）运行

打开Hbuilderx菜单，选择运行--运行到小程序模拟器--微信开发者工具，就可以把uniapp项目在微信开发者工具上面做调试了。

![3.png](https://note.youdao.com/yws/res/6132/WEBRESOURCE1b87eb3ac9d15b4ee170f25acf58d487)

运行成功显示如下：
![1.png](https://note.youdao.com/yws/res/6165/WEBRESOURCE4531ec2d23b565804ad61abc6cc45946)

### （7）配置是否被索引

小程序根目录下的sitemap.json文件用于配置小程序及其页面是否允许被微信索引，文件内容为一个 JSON对象，如果没有sitemap.json则默认为所有页面都允许被索引。

我们配置如下：
![22.png](https://note.youdao.com/yws/res/6084/WEBRESOURCE3ff1cd916f1a9628f5b5589bcddddff7)

## 1.4 git托管项目

- 定义忽略文件
在Hbuilderx打开的项目跟目录下面创建.gitignore文件，添加如下：
![2.png](https://note.youdao.com/yws/res/6099/WEBRESOURCE56e54090b734f4d13c558fc565b81bf5)

这样是为了上传git的时候，这两个文件夹不会上传，因为第一个目录是依赖的包，第一个文件夹是自动生成的项目目录

- 定义跟踪文件
在unpackage文件夹下面新建.gitkeep文件，是为了保证git也要跟踪这个文件夹，否则就不会识别此文件夹了。
![9.png](https://note.youdao.com/yws/res/6077/WEBRESOURCE88853322d87f03f296ac76209a1bd841)

- 把项目提交到本地仓库

1. git init 
2. git add .
3. git commit -m '注释'


打开你的项目根目录，执行下面的命令
![1.png](https://note.youdao.com/yws/res/6134/WEBRESOURCEf3fcd390639aff4816e48596983031d0)
![1.png](https://note.youdao.com/yws/res/6152/WEBRESOURCE0f48b610f871860f8835f7ade9149bbd)

- 把本地项目推送到码云

1. 注册码云账号并登录
2. 配置ssh公钥
3. 配置用户名和邮箱
4. 新建空白仓库
5. 推送到远程仓库

备注：咱们以前操作过，直接做4步和5步即可。

新建uni-test仓库
![1.png](https://note.youdao.com/yws/res/6154/WEBRESOURCE4015b306f670bb5a1b8e610d896ab125)

根据提示执行后两步操作即可
![8.png](https://note.youdao.com/yws/res/6143/WEBRESOURCEc11596786e3a05e3de0bd232f5e37ea6)

操作如下，然后刷新码云仓库，里面显示你新上传的代码代表成功
![1.png](https://note.youdao.com/yws/res/6119/WEBRESOURCE5a6d79d74a0c2ef76104e9e3407146cb)

# 二、tabBar操作

## 2.1创建分支

1. git checkout -b tabbar  创建tabbar分支
2. git branch 查看当前所在的分支

![1.png](https://note.youdao.com/yws/res/6068/WEBRESOURCE7fbf730081e6c1ec5d455c471ae0d9f8)

## 2.2 创建四个页面

### 2.2.1 创建页面

仿照home.vue页面操作，创建其余的分类页面（cate.vue）、购物车页（shop.vue）和我的页面（my.vue）
![2.png](https://note.youdao.com/yws/res/6130/WEBRESOURCE0fb288a6940a25482180ac12ed677cdb)

### 2.2.2 准备静态资源文件

把tabbar需要的图片放在static文件夹中

### 2.2.3 修改pages.json

在Hbuilderx打开的项目的pages.json中配置如下：

```
{
	"pages": [
		{
            "path" : "pages/home/home",
            "style" :                                                                                    
            {
                "navigationBarTitleText": "",
                "enablePullDownRefresh": false
            }
            
        }
        ,{
            "path" : "pages/cate/cate",
            "style" :                                                                                    
            {
                "navigationBarTitleText": "",
                "enablePullDownRefresh": false
            }
            
        }
        ,{
            "path" : "pages/shop/shop",
            "style" :                                                                                    
            {
                "navigationBarTitleText": "",
                "enablePullDownRefresh": false
            }
            
        }
        ,{
            "path" : "pages/my/my",
            "style" :                                                                                    
            {
                "navigationBarTitleText": "",
                "enablePullDownRefresh": false
            }
            
        }
    ],
	"tabBar":{
		"selectedColor":"#E43D33",
		"list":[
			{
				"pagePath":"pages/home/home",
				"text":"首页",
				"iconPath":"static/tab_icons/home.png",
				"selectedIconPath":"static/tab_icons/home-active.png"
			},
			{
				"pagePath":"pages/cate/cate",
				"text":"分类",
				"iconPath":"static/tab_icons/cate.png",
				"selectedIconPath":"static/tab_icons/cate-active.png"
			},
			{
				"pagePath":"pages/shop/shop",
				"text":"购物车",
				"iconPath":"static/tab_icons/cart.png",
				"selectedIconPath":"static/tab_icons/cart-active.png"
			},
			{
				"pagePath":"pages/my/my",
				"text":"我的",
				"iconPath":"static/tab_icons/my.png",
				"selectedIconPath":"static/tab_icons/my-active.png"
			}
		]
	},
	"globalStyle": {
	。。。。
	}
}

```
**注意**
1. 如果配置好了还是不显示tabBar注意把index页面去除，或者把它当成首页，因为默认先渲染的这个页面
2. 如果小程序的底部还是不显示，点击预览或者编译一下即可。

此时页面显示效果如下：
![1.png](https://note.youdao.com/yws/res/6159/WEBRESOURCE1fd2c364ba2d1be4936d52b63f5e7cca)

## 2.3 配置全局头部导航

在Hbuilderx中的pages.json中配置如下：

```
{
	"pages": [
	    。。。	
    ],
	"tabBar":{
		。。。
	},
	"globalStyle": {
		"navigationBarTextStyle": "white",
		"navigationBarTitleText": "惠友到家",
		"navigationBarBackgroundColor": "#E43D33",
    。。。。
	}
}

```
## 2.4 tabBar部分代码推送到码云

1. git branch 查看所在分支
2. git add . 把代码添加到暂存区（如果在tabbar分支上这样操作）
3. git commit -m 'xx' 把代码添加到本地仓库
4. git push -u origin tabbar 把本地tabbar的代码推送到远程tabbar分支上面
5. git checkout master 切换到master主分支
6. git merge tabbar 把tabbar和主分支代码合并
7. git push origin master 把本地master代码推送到远程master分支
8. git branch -d tabbar 把班底tabbar分支删除

![2.png](https://note.youdao.com/yws/res/6061/WEBRESOURCE98a6e761158199c60ffb39a8df07a457)
![2.png](https://note.youdao.com/yws/res/6147/WEBRESOURCE562f576f156d8c23c6067a2f0020ac01)

此时如果刷新你的码云，两个分支都存在且有代码就算成功了。

# 三、首页布局

## 3.1 创建home分支

1. git branch 查看当前所在的分支
2. git checkout -b home 新建home分支
3. 在home分支上面进行开发
![1.png](https://note.youdao.com/yws/res/6160/WEBRESOURCEbfe25efce7da2a7b8ec334912d73d7f6)

## 3.2实现数据网络化请求

我们前面的学的wx.request可以请求后端数据，但是如果想实现请求拦截的功能（登录的时候得用请求拦截），我们可以自己二次封装，或者借用一个第三方包（@escook/request-miniprogram）,具体使用哪种方式，自己决定即可。

使用步骤参考如下或者github（github有的时候打不开，但是讲解比较官方）
[github参考链接](https://github.com/liulongbin1314/request-miniprogram)
[其他参考链接](https://blog.csdn.net/weixin_39411655/article/details/115565689)

- npm init -y 项目根目录下面初始化一个package.json文件
- npm install @escook/request-miniprogram 安装这个第三方包
- main.js中导入这个包并配置

```
import Vue from 'vue'
import App from './App'

// 配置网络请求
import { $http } from '@escook/request-miniprogram'

// 在 uni-app 项目中，可以把 $http 挂载到 uni 顶级对象之上，方便全局调用
uni.$http = $http

// 配置请求的根路径
$http.baseUrl="https://www.fastmock.site/mock/6c3454cb9716e486ccedb6060afe9551/shop"

// 请求拦截器
$http.beforeRequest = function (options) {
  wx.showLoading({
    title: '数据加载中...',
  })
}
// 响应拦截器 就是响应完成之后做一些事
$http.afterRequest = function () {
  wx.hideLoading()
}
。。。。
```

**注意**

注意我们上面配置的项目请求跟地址是我们自己设置的fastmock的根地址或者自己设置你的服务器的根地址

## 3.3 实现轮博图

### 3.3.1模拟轮博图数据

fastmock请求轮博图接口地址如下：

```
https://www.fastmock.site/mock/6c3454cb9716e486ccedb6060afe9551/shop/bannerlist
```
返回数据如下格式：
![1.png](https://note.youdao.com/yws/res/6138/WEBRESOURCEdfdfc35ce0d4073c4fd839bdbea8a4ac)

### 3.3.2 请求轮博图数据

我们在home.vue的js代码中设置如下：

```
<script>
	export default {
		data() {
			return {
				bannerList:[]
			};
		},
		methods:{
			getBannerList:async function(){
				const res=await uni.$http.get('/bannerlist');
				const {data:{list},status}=res.data
				if(status!=200){
					return uni.showToast({
						title:'加载数据失败',
						duration:1000,
						icon:'none'
					})
				}else{
					this.bannerList=list
				}
			}
		},
		onLoad(){
			this.getBannerList()
		}
	}
</script>
```
此时打开微信开发者工具调试器的appData部分如果可以看到数据代表赋值成功。
![1.png](https://note.youdao.com/yws/res/6163/WEBRESOURCEe5efc70cd0b662d60c837cd7b431dd14)

### 3.3.3渲染数据
home.vue视图渲染如下：

```
<template>
	<view>
		<swiper class="swiper-home" indicator-dots="true" autoplay="true" interval="2000"
		circular="true" indicator-color="#000" indicator-active-color="#FF0000">
			<swiper-item v-for="(item,index) in bannerList" :key="index">
				<image :src="item.picUrl"></image>
			</swiper-item>
		</swiper>
	</view>
</template>
```
样式设置如下：

```
<style lang="scss">
.swiper-home{
	width:100%;
	background-color: #E43D33;
	swiper-item{
		width:100%;
		image{
			width:100%;
			height:300rpx;
		}
	}
}
</style>
```
显示效果如下：
![1.png](https://note.youdao.com/yws/res/6069/WEBRESOURCE51be694124518d93bd4da9c07c138a64)

**注意**
轮博图的圆角是因为从苏宁网站的移动端拔下来的图。

### 3.3.4配置分包

因为小程序要求体量不能太大，所以我们一般是把主页和tabbar页面设置成主包，其他的页面需要的时候再下载，设置成分包，方便管理。

- 项目根目录创建subpkg文件夹（文件夹名随便起）
- pages.json配置如下：

```
{
。。。
	"globalStyle": {
		。。。
	},
	"subPackages":[
		{
			"root":"subpkg",
			"pages":[]
		}
	]
}

```
- subpkg文件夹中新建商品详情页（goods-detail）
![1.png](https://note.youdao.com/yws/res/6124/WEBRESOURCE2cdcd460f9c61750ce1ad5172cd7084b)

- pages.json文件中自动生成下面的配置

```
{
。。。。
    "subPackages":[
		{
			"root":"subpkg",
			"pages":[{
                    "path" : "goods-detail/goods-detail",
                    "style" :                                                                                    
                {
                    "navigationBarTitleText": "",
                    "enablePullDownRefresh": false
                }
                
                }
            ]
		}
	]
}
```
### 3.3.5跳转到详情页

我们需要实现的是点击轮博图的任意一张图都能跳转到详情页面，所以在home.vue页面更改如下：

```
。。。
	<navigator :url="'/subpkg/goods-detail/goods-detail?goodid='+item.id">
		<image :src="item.picUrl"></image>
	</navigator>
。。。
```
此时点击轮博图的图片能跳转到详情页边并且能传递过去商品id

## 3.4 实现分类展示

### 3.4.1分类数据接口

fastmock上面我们的分类接口地址如下：

```
https://www.fastmock.site/mock/6c3454cb9716e486ccedb6060afe9551/shop/cates
```
请求方式：get
返回数据格式：
![11.png](https://note.youdao.com/yws/res/6072/WEBRESOURCE6f313bdd6924217e9f563b2f541686b4)

### 3.4.2 获取动态数据

home.vue的js中定义空数据组cateList,然后请求fastmock接口获取数据并给cateList赋值。

```
<script>
	export default {
		data() {
			return {
				bannerList:[],
				cateList:[]
			};
		},
		methods:{
			// 获取所有的轮博图列表
			getBannerList:async function(){
			。。。
			},
			// 获取所有的分类信息
			getCateList:async function(){
				const res=await uni.$http.get('/cates')
				const {data:{cateList},status}=res.data
				if(status!=200){
					return uni.showToast({
						title:'加载数据失败',
						duration:1000,
						icon:'none'
					})
				}else{
					this.cateList=cateList
				}
			}
		},
		onLoad(){
			//调用获取分类数据的方法
			this.getCateList();
		}
	}
</script>
```
此时打开微信开发者工具如果appData中的cateList有数据，代表获取信息成功。

### 3.4.3 渲染页面结构

home.vue渲染视图如下：

```
<!-- 获取分类数据结构 -->
	<view class="cates">
		<view class="cate-item" v-for="(cateItem,cateIndex) in cateList" :key="cateIndex">
			<image :src="cateItem.catePic"></image>
			<text>{{cateItem.cateName}}</text>
		</view>
	</view>
```
设置样式如下：

```
.cates{
	width:100%;
	height:320rpx;
	border-bottom:1rpx solid #C7C7C7;
	display: flex;
	flex-wrap: wrap;
	justify-content: space-around;
	align-content: center;
	.cate-item{
		width:20%;
		height:150rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-around;
		align-items: center;
		image{
			width:78rpx;
			height:78rpx;
		}
	}
}
```
显示效果如下：
![1.png](https://note.youdao.com/yws/res/6112/WEBRESOURCE1d62be7b7a228d1bcab4cba3a508b9d0)

### 3.4.4点击导航跳转到分类页

home.vue的分类导航部分添加事件

```
<view class="cates">
	<view class="cate-item" v-for="(cateItem,cateIndex) in cateList" :key="cateIndex" @click="goToCate(cateItem)">
		<image :src="cateItem.catePic"></image>
		<text>{{cateItem.cateName}}</text>
	</view>
</view>
```
处理跳转事件：

```
// 跳转到分类页面
	goToCate:function(cateItem){
		if(cateItem.cateName=="分类"){
			uni.switchTab({
				url:'/pages/cate/cate'
			})
		}
	}
```
### 3.4.5 首页楼层处理

#### （1）定义楼层接口
fastmock的楼层接口地址：

```
https://www.fastmock.site/mock/6c3454cb9716e486ccedb6060afe9551/shop/floors
```
请求方式：get
请求数据格式：
![1.png](https://note.youdao.com/yws/res/6149/WEBRESOURCE12717e1f408f64181c34fabd35a87b21)

#### （2）获取楼层数据

home.vue的js中定义空数组floorList,然后把请求的fastmock的数据赋值给floorList数组当中

```
<script>
	export default {
		data() {
			return {
			    。。。
				floorList:[]
			};
		},
		methods:{
		    。。。
			// 获取楼层数据
			getFloorList:async function(){
				const res=await uni.$http.get('/floors')
				const {data:{floorList},status}=res.data
				if(status!=200){
					return uni.showToast({
						title:'加载数据失败',
						duration:1000,
						icon:'none'
					})
				}else{
					this.floorList=floorList
				}
			}
		},
		onLoad(){
			。。。
			this.getFloorList()
		}
	}
</script>
```
此时打开微信开发者工具的appData中如果有数据代表成功。

#### （3）渲染页面结构
home.vue的视图结构如下：

```
<!-- 楼层部分的页面结构 -->
		<view class="floor-list">
			<view v-for="(floorItem,floorIndex) in floorList" :key="floorIndex" class="floor-item">
				<view class="floor-title">{{floorItem.floor_title}}</view>
				<view class="floor-con">
					<view v-for="(floorSubItem,floorSubIndex) in floorItem.floor_con" class="sub-item">
						<image :src="floorSubItem.imgPic"></image>
						<view class="proname">{{floorSubItem.name}}</view>
						<view class="proprice">{{floorSubItem.price}}</view>
					</view>
				</view>
			</view>
		</view>
```
home.vue添加样式如下：

```
.floor-list{
	width:100%;
	.floor-item{
		width:100%;
		height:840rpx;
		background-color: #fff;
		.floor-title{
			height:60rpx;
			line-height: 60rpx;
			font-weight: 900;
		}
		.floor-con{
			width:100%;
			height:400rpx;
			display: flex;
			flex-wrap: wrap;
			justify-content: space-around;
			align-items: center;
			.sub-item{
				width:50%;
				height:400rpx;
				display: flex;
				flex-direction: column;
				justify-content: space-around;
				align-items: center;
				image{
					width:220rpx;
					height:220rpx;
				}
			}	
		}
		
	}
}
```
显示效果如下：
![1.png](https://note.youdao.com/yws/res/6067/WEBRESOURCEb56cf24c52733a9277ec92bca9b2aa3b)

#### （4）点击楼层图片跳转商品列表页面

第一步：创建商品列表页面（goods_list）
![2.png](https://note.youdao.com/yws/res/6157/WEBRESOURCE56a2a4de8527617577ebf15c30f16dd0)

第二步：给每个商品信息项添加一个自定义数据url
![1.png](https://note.youdao.com/yws/res/6128/WEBRESOURCE4a0c4980c0a928eb85f6286a91d541a4)
**备注**
上面的属性可以用js动态添加，也可以自己修改模拟数据，手动添加
第三步：页面添加navigator标签
![2.png](https://note.youdao.com/yws/res/6102/WEBRESOURCEdb407e94dfa4b93efacd4d18b6783bd5)
此时点击每一个商品列表的图片都能跳转到商品列表页面。

### 3.4.6 分支合并
1. git add . 
2. git commit -m '完成了首页'
3. git push -u origin home 远程创建home分支
4. git checkout master 切换到主分支
5. git merge home 和home分支合并
6. git branch -d home

![1.png](https://note.youdao.com/yws/res/6120/WEBRESOURCEdc0d6b0c93096a49a96fe4cf78d0832c)
![2.png](https://note.youdao.com/yws/res/6145/WEBRESOURCE16015af358aac6bea4d0f2f2b82c8c0b)

# 四、分类页面

## 4.1 git操作

1. git branch 查看当前所在的分支
2. git checkout -b cate 创建cate分支

## 4.2左右分类布局

左侧使用的scroll-view组件，核心是必须设置scroll-y属性和固定高度（动态获取的页面的高度并赋值）才会起作用
cate.vue视图如下：

```
<!-- 分类页面 -->
		<view class="cate-container">
			<scroll-view scroll-y :style="{height:h+'px'}" class="cate-left">
				<view>11111111</view>
				<view>11111111</view>
				<view>11111111</view>
				。。。
			</scroll-view>
			<scroll-view scroll-y :style="{height:h+'px'}" class="cate-right">
				<view>11111111</view>
				<view>11111111</view>
				<view>11111111</view>
			    。。。
			</scroll-view>
		</view>
```
cate.vue样式如下：

```
<style lang="scss">
.cate-container{
	width:100%;
	height:600rpx;
	display:flex;
	.cate-left{
		width:100px;
	}
	.cate-right{
		
	}
}
</style>
```
cate.vue逻辑如下：

```
<script>
	export default {
		data() {
			return {
				h:0
			};
		},
		onLoad:function(){
			const systemInfo=uni.getSystemInfoSync();//获取设备相关的信息
			const systemHeight=systemInfo.windowHeight;//获取设备的页面高度
			this.h=systemHeight
		}
	}
</script>
```
**注意**
上面的view里面包裹111内容的是测试内容，需要数据非常多才能出现滑动效果。
## 4.3 左侧样式
左侧结构如下：

```
<scroll-view scroll-y :style="{height:h+'px'}" class="cate-left">
	<block v-for="(cateItem,i) in cateList" :key="i">
		<view :class="['cate-left-item',i===active?'active':'']" @click="changeNav(i)">{{cateItem.cateName}}</view>
	</block>
</scroll-view>
```

添加样式如下：

```
.cate-left-item{
	height:84rpx;
	line-height:84rpx;
	padding-left:12rpx;
	background-color: #F7F7F7;
	&.active{
		background-color: #fff;
		position: relative;
		&::before{
			content:'';
			display:block;
			width:3px;
			height:40rpx;
			background-color: #FF0000;
			position: absolute;
			top:24rpx;
			left:0;
        }
	}
}
```
左侧的数据如下：

```
<script>
	export default {
		data() {
			return {
				h:0,
				cateList:[],
				active: 0
			};
		},
		methods:{
			getCateList:async function(){
				const res=await uni.$http.get('/cates')
				const {data:{cateList},status}=res.data
				if(status!=200){
					return uni.showToast({
						title:'加载数据失败',
						duration:1000,
						icon:'none'
					})
				}else{
					this.cateList=cateList
				}
			},
			// 切换导航的处理事件
			changeNav:function(i){
				this.active=i
			}
		},
		onLoad:function(){
			const systemInfo=uni.getSystemInfoSync();//获取设备相关的信息
			const systemHeight=systemInfo.windowHeight;//获取设备的页面高度
			this.h=systemHeight
			// 获取商品分类信息
			this.getCateList()
		}
	}
</script>
```

此时用户移动到哪一个左侧的导航菜单上面的时候，会显示一个左侧红色的导航条。
## 4.4 右侧数据展示

### 4.4.1 修改分类接口

我们修改一下分类接口，里面的children属性代表这个分类下面的所有的商品信息。
![16.png](https://note.youdao.com/yws/res/6090/WEBRESOURCE2e69cfffbf2cb3b8403c85387f908a5a)

### 4.4.2 获取右侧数据

```
<script>
	export default {
		data() {
			return {
			    。。。。
				goodsList:[]
			};
		},
		methods:{
			getCateList:async function(){
				const res=await uni.$http.get('/cates')
				const {data:{cateList},status}=res.data
				console.log(cateList)
				if(status!=200){
					return uni.showToast({
						title:'加载数据失败',
						duration:1000,
						icon:'none'
					})
				}else{
					this.cateList=cateList
					// 获取右侧的数据并给goodsList赋值
					this.goodsList=cateList[0].children
				}
			},
			// 切换导航的处理事件
			changeNav:function(i){
				this.active=i
				// 点击左侧分类切换的时候把当前项的分类下面的所有商品数据赋值
				this.goodsList=this.cateList[i].children
			}
		},
	    。。。。
	}
</script>
```
### 4.4.4 渲染右侧数据

右侧结构如下：

```
<scroll-view scroll-y :style="{height:h+'px'}" class="cate-right">
	<view v-for="(goodItem,goodIndex) in goodsList" :key="goodIndex" class="pro-content">
		<image :src="goodItem.picUrl" class="pro-pic"></image>
		<view class="pro-right">
			<view class="pro-name">{{goodItem.pname}}</view>
			<view class="pro-price">价格：{{goodItem.price}}</view>
		</view>
	</view>	
</scroll-view>
```
右侧样式如下：

```
.cate-right{
		.pro-content{
			width:100%;
			height:260rpx;
			border-bottom:1rpx solid #f0f0f0;
			display: flex;
			justify-content: space-between;
			align-items: center;
			.pro-pic{
				width:200rpx;
				height:200rpx;
			}
			.pro-right{
				flex:1;
				padding-left:20rpx;
			}
			
		}
	}
```
显示效果如下：
![1.png](https://note.youdao.com/yws/res/6087/WEBRESOURCE0779dc57e50dba3eac9653c3bf0bc0ee)

### 4.4.5git提交
1. git add .
2. git commit -m '完成了分类功能'
3. git push -u origin cate
4. git checkout master
5. git merge cate
6. git push 
6. git branch -d cate

# 五、搜索组件

## 5.1创建分支

git checkout -b search

## 5.2创建搜索组件
选择项目下面的components文件夹，鼠标右键选择新建组件，生成search组件即可。
![2.png](https://note.youdao.com/yws/res/6111/WEBRESOURCE7c8602ecd7ebbf2196bc55f6890abb9d)

在需要使用组件的页面，比如我们在cate.vue页面添加如下代码就可以使用这个组件了。

```
<!-- 搜索组件 -->
<search></search>
```
## 5.3搜索组件结构和样式实现

search.vue结构如下：

```
<template>
	<view class="search-container">
		<view class="search-inner">
			<uni-icons type="search" size="20"></uni-icons>
			<text>搜索</text>
		</view>
	</view>
</template>
```
search.vue样式如下：

```
<style lang="scss">
	.search-container{
		width:100%;
		height:100rpx;
		background-color: #E43D33;
		.search-inner{
			width:90%;
			height:80rpx;
			background-color: #fff;
			border-radius: 40rpx;
			margin:0 auto;
			display: flex;
			justify-content: flex-start;
			align-items: center;
			padding-left:10rpx;
		}
	}
</style>
```
效果如下：
![11.png](https://note.youdao.com/yws/res/6100/WEBRESOURCEa6aae7f43dd5c1a16adf48df3de5238f)

同时我们还需要修改cate.vue中获取页面高度部分的代码，我们得刨去搜索框的高度。

![11.png](https://note.youdao.com/yws/res/6097/WEBRESOURCEc62103fb9401a0663ef5c7def694a037)

## 5.4跳转到搜索页

在search.vue中绑定click事件
![1.png](https://note.youdao.com/yws/res/6151/WEBRESOURCE9e707e28a34f34a3c799633a7a6582cd)
在分包subpkg文件夹中新建页面goods-search页面
![1.png](https://note.youdao.com/yws/res/6121/WEBRESOURCE6c1e9023fc47d259fcaa3fd09013d143)
在cate.vue中接收传递的事件并处理
![2.png](https://note.youdao.com/yws/res/6133/WEBRESOURCEe8905546a893b44aef2a5186a74f1082)

## 5.5 首页也是用搜索组件

home.vue添加结构：

```
<!-- 搜索组件 -->
		<view class="home-search-container">
			<search @click="goToSearch"></search>
		</view>
```
事件如下：

```
methods:{
			// 搜索框的事件
			goToSearch:function(){
				uni.navigateTo({
					url:'/subpkg/goods-search/goods-search'
				})
			},
			。。。
}
```
防止搜索框移动添加如下属性：

```
<style lang="scss">
.home-search-container{
	position: sticky;
	top:0;
	z-index: 999;
}
</style>
```
# 六、搜索页面

## 6.1 搜索页面头部搜索框

前面的home页面和cate页面的搜索框不是真正的搜索框，只是模拟样式，真正实现搜索功能的是搜索页面的这个组件，所以我们查看uniapp官网查看搜索组件的用法
![1.png](https://note.youdao.com/yws/res/6076/WEBRESOURCEe098be7d0d537536bf91ddab97721c27)

## 6.2search页面布局实现

search.vue添加结构如下：

```
<template>
	<view>
		<view class="search-container">
			<uni-search-bar @input="input" :radius="40" cancelButton="none"></uni-search-bar>
		</view>
	</view>
</template>
```
添加样式如下：（保证搜索框一直吸附在搜索页面的顶部）

```
<style lang="scss">
.search-container{
	height:100rpx;
	background-color: #E43D33;
	position: sticky;
	top:0;
	z-index:999;
}
</style>
```

添加事件如下：（用户输入的时候可以获取用户输入的内容）

```
methods:{
	input:function(e){
		console.log(e)
	}
}
```
## 6.3防止用户输入不停发送请求
上面的输入事件用户只要输入一个字母就会打印，也就意味着将来我们发送后端请求的时候，用户还没输完的时候就会不停的给后台发送请求，这样需要优化。
所以我们可以设置500毫秒以内不发送请求，500毫秒以后再发送请求，具体代码如下：

```
export default {
		data() {
			return {
				// 初始化定时器为空
				time:null,
				// 用户输入的关键词
				keyword:''
			};
		},
		methods:{
			input(e){
				// 每次使用先清空定时器
				clearTimeout(this.timer);
				this.timer=setTimeout(()=>{
					this.keyword=e
				},500)
			}
		}
	}
```
**注意**
上面的input函数不能定义成input:function(){}的函数

## 6.4实现搜索列表

我们实现搜索列表展示思路应该是把用户输入的内容发送给后端，后端接受以后通过模糊查询把查询的结果返回给前端，我们暂时没写后台，可以在fastmock上面模拟一些返回数据，就请求水果即可（因为我模拟的是水果相关的数据）
#### 6.4.1模拟后端数据

接口地址如下：
```
https://www.fastmock.site/mock/6c3454cb9716e486ccedb6060afe9551/shop/search
```
模拟数据如下：
![1.png](https://note.youdao.com/yws/res/6106/WEBRESOURCEc9bb5999957745d53e6753ecc0d6b9e7)

因为我们没有办法接受关键字，所以用户输入什么都会返回上面的模拟数据，知道原因即可，或者自己写后台接口。

#### 6.4.2 请求搜索数据

- data中定义空数组

```
data() {
	return {
		。。。
		// 搜索数据的数组初始化
		searchList:[]
	};
}
```
- methods中定义获取搜索列表的方法

```
methods:{
	input(e){
		。。。		
	},
	async getSearchContent(){
		if(this.keyword.length==0){
			this.searchList=[];
			return
		}else{
			const res=await uni.$http.get('/search')
			const {data,status}=res.data;
			if(status!=200){
				alert('获取数据失败')
			}else{
				this.searchList=data
			}
		}
	}
}
```
- 用户输入的时候调用这个方法

```
methods:{
	input(e){
		// 每次使用先清空定时器
		clearTimeout(this.timer);
		this.timer=setTimeout(()=>{
				this.keyword=e
		// 获取搜索数据
		this.getSearchContent()
	},500)
    },
    。。。
}

```
- 渲染列表结构

```
<!-- 显示搜索列表 -->
	<view class="search-list">
		<view class="search-item" v-for="(item,index) in searchList" :key="index">
		{{item.word}}
		</view>
	</view>
```
- 添加样式

```
.search-list{
	width:100%;
	background-color: #fff;
	// border-bottom:1rpx solid #C0C4CC;
	// border-top:1rpx solid #C0C4CC;
	margin-top:10rpx;
	display: flex;
	flex-wrap: wrap;
	justify-content: flex-start;
	align-content: center;
	.search-item{
		width:100rpx;
		height:50rpx;
		background-color: #F0F0F0;
		border-radius: 20rpx;
		text-align: center;
		line-height: 50rpx;
		margin:8rpx;
	}
	
}
```
显示如下：
![1.png](https://note.youdao.com/yws/res/6108/WEBRESOURCE0f860415920412ca8cb61aba01e02aa2)

- 点击搜索项跳转到商品详情页

```
<!-- 显示搜索列表 -->
		<view class="search-list">
			<view class="search-item" v-for="(item,index) in searchList" :key="index" @click="goToDetail(index)">
				{{item.word}}
			</view>
		</view>
```
定义跳转方法：

```
methods:{
		。。。
			// 跳转到商品详情页
	goToDetail(id){
	    uni.navigateTo({
				url:'/subpkg/goods-detail/goods-detail?goodId='+id
			})
		}
	}
```
此时点击搜索出来的选项可以跳转到我们前面定义的搜索项。

## 6.5 实现搜索历史展示

### 6.5.1搜索历史布局处理
- data中定义家假搜索历史数组
 
```
data() {
	return {
		。。。
		// 搜索历史初始化
		historyList:['水果','家具','充电器']
		};
	}
```
- 渲染历史结构

```
<!-- 显示搜索历史 -->
	<view class="history-container">
		<view class="history-title">
			<text>搜索历史</text>
			<uni-icons type="trash" size="20"></uni-icons>
		</view>
		<view class="history-content">
			<view class="history-item" v-for="(historyItem,historyIndex) in historyList" :key="historyIndex">{{historyItem}}
			</view>
		</view>
	</view>
```
- 添加样式

```
.history-container{
	margin-top:20rpx;
	width:100%;
	padding:0 10rpx;
	box-sizing: border-box;
	.history-title{
		width:100%;
		height:40rpx;
		display: flex;
		justify-content: space-between;
		align-items: center;
	}
	.history-content{
		width:100%;
		background-color: #fff;
		// border-bottom:1rpx solid #C0C4CC;
		// border-top:1rpx solid #C0C4CC;
		margin-top:10rpx;
		display: flex;
		flex-wrap: wrap;
		justify-content: flex-start;
		align-content: center;
		.history-item{
			width:100rpx;
			height:50rpx;
			background-color: #F0F0F0;
			border-radius: 20rpx;
			text-align: center;
			line-height: 50rpx;
			margin:8rpx;
		}
	}
}
```
## 6.6 搜索历史和搜索列表二选一

思路：
如果用户没有输入内容，也就是searchList数组为空的时候，显示搜索历史，否则显示搜索列表
![11.png](https://note.youdao.com/yws/res/6139/WEBRESOURCEef5b8152c2716fef86a0719b75871a59)

## 6.7 把搜索关键字在历史记录显示
思路：
用户输入内容的时候把用户输入的关键字保存到历史记录的数组中去，当然满足两个条件：
1. 新搜索的内容在头部显示
2. 输入重复的内容就在历史记录数组中只显示一个即可

![1.png](https://note.youdao.com/yws/res/6113/WEBRESOURCEbe9613bf0d4b6b8e6d36686a06867fa8)

## 6.8持久保存历史记录

思路：
我们需要把用户输入的数组存储到本地存储中才方便持久保存。
- 保存方法中存储数据

```
// 保存历史记录
saveHistory(){
	let index=this.searchList.findIndex(item=>{
			return item===this.keyword
	})
	if(index==-1){
		this.historyList.unshift(this.keyword)
		// 把历史记录数组存储到本地存储
	    uni.setStorageSync('kw',JSON.stringify(this.historyList))
	}
				
}
```
- 页面加载的时候读取历史记录数据

```
onLoad(){
	this.historyList=JSON.parse(uni.getStorageSync('kw')||'[]')
}

```
## 6.9清空历史记录
- 删除按钮绑定单击事件

```
<uni-icons type="trash" size="20" @click="clearHistory"></uni-icons>
```
- 完成删除逻辑

```
methods:{
    。。。
   // 清空历史记录
	clearHistory(){
		this.historyList=[];
		uni.setStorageSync('kw','[]')
	} 
}
```
## 7.0 点击搜索跳转到商品列表

思路：
我们点击任意一个搜索历史，跳转到商品列表页面
- 绑定单击事件

```
<view class="history-content">
	<view class="history-item" v-for="(historyItem,historyIndex) in historyList" :key="historyIndex" @click="goToGoods(historyItem)">{{historyItem}}</view>	
</view>
```
- 实现单击事件

```
// 跳转到商品列表
	goToGoods(item){
		uni.navigateTo({
			url:'/subpkg/goods-list/goods-list?query='+item
	    })
	}
```
## 7.1 git提交
先确保自己在search主分支上面，然后依次执行下面的操作

1. git add .
2. git commit -m '完成了搜索功能'
3. git push -u origin search
4. git checkout master 切换到主分支
5. git merge search 合并分支
6. git push  推送到远程的主分支
7. git branch -d search  删除搜索分支

# 七、商品列表

## 7.1 创建商品列表分支

1. git brach 查看当前所在分支
2. git checkout -b goodslist 创建商品列表分支

## 7.2 定义请求接口

正常的请求后端接口至少应该保留四个如下参数：
1. query 代表查询的关键字
2. cname 当前商品所属的分类(或者传递商品所属分类的编号，根据你自己的数据而定)


还是因为我们用的fastmock，我们可以发送，但是它无法解析处理，所以我们模拟10条数据，页面固定设置为1即可。（也可以自己设定接口）

![1.png](https://note.youdao.com/yws/res/6091/WEBRESOURCEed2c8997626f6ce6d600de050dfdfb3c)

## 7.3 渲染UI结构

goods-list页面结构如下：

```
<template>
	<view>
		<view class="goods-list">
			<view class="goods-item" v-for="(goodItem,goodIndex) in goodsList" :key="goodIndex">
				<image :src="goodItem.goodPic" class="goods-pic"></image>
				<view class="goods-info">
					<view>{{goodItem.goodName}}</view>
					<view class="price">{{goodItem.price}}</view>
				</view>
			</view>
		</view>
	</view>
</template>
```
页面样式如下：

```
<style lang="scss">
.goods-list{
	.goods-item{
		width:100%;
		height:220rpx;
		margin-bottom:10rpx;
		display: flex;
		border-bottom:1px solid #f0f0f0;
		.goods-pic{
			display: block;
			width:200rpx;
			height:200rpx;
			margin-right:10rpx;
		}
		.goods-info{
			flex:1;
			display: flex;
			flex-direction: column;
			justify-content: space-around;
			.price{
				color:#FF5A5F;
			}
		}
		
	}
}
</style>
```
显示结果如下：
![1.png](https://note.youdao.com/yws/res/6141/WEBRESOURCE9bbc541231325363f7420132ebef54b4)

## 7.4 过滤器实现商品价格

我们需要价格前面拼接‘¥’而且得到的数据保留1位小数点，所以我们在goods-list页面定义过滤器如下：

```
export default {
		data() {
			。。。
		},
		onLoad:async function(options){
			。。。
		},
		// 定义处理商品价格的过滤器
		filters:{
			handlePrice:function(num){
				return '¥'+num.toFixed(1)
			}
		}
	}
```
在页面结构使用过滤器如下：

```
<view class="goods-info">
    <view>{{goodItem.goodName}}</view>
		<view class="price">{{goodItem.price|handlePrice}}</view>
	</view>
```
此时如下显示：
![1.png](https://note.youdao.com/yws/res/6137/WEBRESOURCE5cbbb17a909a89adcee09340a0bfd004)

## 7.5上拉加载更多
- 修改pages.json,设置运行下拉刷新和下拉刷新的距离
![2.png](https://note.youdao.com/yws/res/6164/WEBRESOURCE1cd602df772dc119555b9db8be2a769b)

-实现js代码逻辑

```
<script>
	export default {
		data() {
			return {
				queryInfo:{
					// 搜索关键词
					query:'',
					// 商品所属分类
					cname:'',
					// 当前的页码
					pagenum:1,
					// 每页显示多少条数据
					pagesize:10
				},
				// 商品数组
				goodsList:[]
			};
		},
		onLoad:function(options){	
			this.queryInfo.query=options.query||''
			this.queryInfo.cname=options.cname||''
			// 获取接口并且给商品数组赋值
			this.getGoodsList()
		},
		// 定义处理商品价格的过滤器
		filters:{
			handlePrice:function(num){
				return '¥'+num.toFixed(1)
			}
		},
		methods:{
			async getGoodsList(){
				const res=await uni.$http.get('/goods',this.queryInfo)
				const {data,status}=res.data
				if(status!=200){
					return uni.showToast({
						title:'加载数据失败',
						duration:1000,
						icon:'none'
					})
				}else{
					// this.goodsList=data 原来没有添加上拉加载更多的写法
					this.goodsList=[...this.goodsList,...data]
				}
			}
		},	
		// 添加上拉触底事件
		onReachBottom:function(){
			this.queryInfo.pagenum++;//让页码增加
			this.getGoodsList();
		}
	}
</script>
```
**备注**
因为页面加载的时候需要请求商品数据，上拉触底事件也需要请求商品数据，所以把核心代码封装成两个一个getGoodsLust方法，多次调用，上面的代码改动比较多，请认真比较。

## 7.6 请求数据实现防抖处理

- data中定义节流阀
- 根据不同情况开启和关闭节流阀
![5.png](https://note.youdao.com/yws/res/6082/WEBRESOURCEb166165f9115c95109348f37a24a297b)

## 7.7 跳转到商品详情页
![0.png](https://note.youdao.com/yws/res/6096/WEBRESOURCE8746d06c49a0cc4224e6a88878a7aa7a)

## 7.8 分支合并

在goodslist分支执行步骤1和2、3、4
在master主分支执行5、6、7

1. git add .
2. git commit -m '完成了商品列表功能'
3. git push -u origin goodslist
4. git checkout master
5. git merge goodslist 
6. git push 
7. git branch -d goodslist 

# 八、商品详情

## 8.1创建商品详情分支


```
git checkout -b gooddetail

```
## 8.2 模拟数据

我们在fastmock模拟数据如下：



**备注**
我们拿到的商品详情数据是固定的，如果是真实的接口，传递不同的商品id就会显示不同的商品详情的具体信息。


## 8.3 获取商品详情数据

- data中定义goodInfo对象

```
data() {
	return {
	    // 定义商品详情信息对象
		goodInfo:{}
	};
}
```
- methods中定义获取商品详情的方法

```
methods:{
	async getGoodDetail(goodId){
		const res=await uni.$http.get('/detail',{"goodId":goodId});
		const {data,status}=res.data
		if(status!=200){
			return uni.showToast({
				title:'加载数据失败',
				duration:1000,
				icon:'none'
			})
			}else{
				this.goodInfo=data
			}
	}
}
onLoad(){
	this.getGoodDetail()
}
```
## 8.4渲染页面结构

```
<!-- 商品轮博图部分 -->
		<swiper class="good-container" indicator-dots=true autoplay="true" duration="2000" circular="true">
			<swiper-item v-for="(item,index) in goodInfo.pics"class="banner-item">
				<image :src="item.bigPic"></image>
			</swiper-item>
		</swiper>
```
页面样式如下：

```
<style lang="scss">
.good-container{
	height:600rpx;
	.banner-item{
		width:100%;
		height:600rpx;
		image{
			width:100%;
			height:600rpx;
		}
	}
}	

</style>
```
## 8.5 图片预览

- 图片绑定预览事件

```
<image :src="item.bigPic" @click="preview(index)"></image>
```

- 处理预览事件

```
export default {
		data() {
			return {
				// 定义商品详情信息对象
				goodInfo:{}
			};
		},
		methods:{
			async getGoodDetail(goodId){
			    。。。
			},
			// 图片预览
			preview(index){
				let arr=[];
				this.goodInfo.pics.map(item=>{
					arr.push(item.bigPic)
				})
				uni.previewImage({
					urls:arr,
					current:index
				})
				console.log(index)
			}
		},
		onLoad(){
			this.getGoodDetail()
		}
	}
```
**注意**
上面的预览有点小问题，也许是接口的问题，只能预览第一张大图。

## 8.6 商品信息部分

添加结构如下：

```
<!-- 商品信息区域 -->
	    <view class="good-info">
			<view>{{goodInfo.goods_name}}</view>
			<view class="price">¥{{goodInfo.goods_price}}</view>
			<view>{{goodInfo.goods_shopAddress}}</view>
			<view>联系客服</view>
		</view>
		<view class="good-attr">
			<view>商品详细图示区域</view>
			<image :src="goodInfo.goodAttr.pic1"></image>
			<image :src="goodInfo.goodAttr.pic2"></image>
			<image :src="goodInfo.goodAttr.pic3"></image>
			<image :src="goodInfo.goodAttr.pic4"></image>
			<image :src="goodInfo.goodAttr.pic5"></image>
		</view>
```
添加样式如下：

```
.good-info{
	width:100%;
	height:300rpx;
	display: flex;
	flex-direction: column;
	justify-content: space-around;
	.price{
		color:#FF5A5F;
	}
}
.good-attr{
	image{
		width:100%;
		// 取消图片底部的空白间隙
		display:block;
	}
}
```
## 8.7 商品详情底部导航
商品详情页面一半会显示下面的样式，我们使用uniapp中的uni-goods-nav实现，可以参照文档使用方法
![15.png](https://note.youdao.com/yws/res/6063/WEBRESOURCEec64b407b0d12e3b1bc5a052a2e7cdc2)

- data中添加配置options和buttonGroup

```
data() {
			return {
				// 定义商品详情信息对象
				goodInfo:{},
				// 商品导航部分
				 options: [{
				            icon: 'headphones',
				            text: '客服'
				        }, {
				            icon: 'shop',
				            text: '店铺',
				            info: 2,
				            infoBackgroundColor:'#007aff',
				            infoColor:"red"
				        }, {
				            icon: 'cart',
				            text: '购物车',
				            info: 2
				        }],
				        buttonGroup: [{
				          text: '加入购物车',
				          backgroundColor: '#ff0000',
				          color: '#fff'
				        },
				        {
				          text: '立即购买',
				          backgroundColor: '#ffa200',
				          color: '#fff'
				        }
				        ]
			}
```
- 页面添加组件

```
<!-- 底部商品导航部分 -->
<view class="good-nav">
	<uni-goods-nav :fill="true"  :options="options" :buttonGroup="buttonGroup"  @click="onClick" @buttonClick="buttonClick" />
</view>
```
- 商品详情页面根元素添加padding

```
.good-detail-container{
	// 设置底部的padding,避免压着页面
	padding-bottom:100rpx;
	//省略好多样式
	.....
	.good-nav{
		width:100%;
		position: fixed;
		left:0;
		bottom:0;
		z-index:999;
	}
}
```
此时显示效果如下：
![1.png](https://note.youdao.com/yws/res/6098/WEBRESOURCEd20a24e937d872d7b007cf518c52c107)

**使用说明**

## 8.8跳转到购物车页面

- good-detail页面的的组件添加onClick事件（这个上面步骤就写好了）

```
<uni-goods-nav :fill="true"  :options="options" :buttonGroup="buttonGroup"  @click="onClick" @buttonClick="buttonClick" />
```
- 完成跳转功能

```
methods:{
    onClick(e){
	    if(e.content.text==='购物车'){
			uni.switchTab({
				url:"/pages/shop/shop"
			})
		}
	}
}
```
此时我们点击购物车文字和图标可以跳转到购物车页面
![6.png](https://note.youdao.com/yws/res/6150/WEBRESOURCEbf1684a2496812d6119cc801032f180f)

## 8.9 git提交
1. git add . 添加到暂存区
2. git commit -m '完成了商品详情功能'
3. git push -u origin gooddetail 提交到远程的gooddetail分支
4. git checkout master 切换到主分支
5. git merge gooddetail 合并分支
6. git push  把本地mater代码提交到远程的master主分支
7. git branch -d gooddetail

# 九、实现加入购物车功能

## 9.1创建cart分支

```
git checkout -b cart
```
## 9.2 配置vuex

因为购物车中的数据在多个页面都需要使用，所以建议我们使用vuex进行数据共享。

- 项目根目录新建store文件夹，里面新建store.js

```
import Vue from 'vue'
import Vuex from 'vuex'

Vue.use(Vuex)
const store=new Vuex.Store({
	modules:{
		
	}
})
export default store;
```
- main.js引入store.js
![2.png](https://note.youdao.com/yws/res/6115/WEBRESOURCEfea6bedd059e5af0a05859a37a0ca3cd)

## 9.2 创建购物车模块

- store目录下面新建cart.js，代码如下：

```
export default{
	// 开启命名空间
	namespaced:true,
	state:()=>({
		// 每个商品的信息对象包含下面6个属性：goods_id,goods_name,goods_price,goods_count,goods_small_logo,goods_state
		cart:[]
	}),
	mutations:{},
	getters:{}
}
```
**备注**
这个js文件是专门处理购物车的数据的。
- store/store.js引入购物车模块的js
![1.png](https://note.youdao.com/yws/res/6080/WEBRESOURCE7ca71aea37bdb358da6b77e43bb5a540)

## 9.3 点击加入购物车
- cart.js中的mutaions中定义一个添加到购物车的方法

```
mutations:{
		// 定义添加到购物车方法
	addToCart(state,goods){
		//判断要添加的商品信息在state数组中是否存在，存在就数量+1，不存在就存储到cart数组中
	    const findResult=state.cart.find(item=>item.goods_id===goods.goods_id);
		if(!findResult){
			state.cart.push(goods)
		}else{
		    findResult.goods_count++;
		}
	}
}
。。。
```
- 商品详情页调用方法

```
<script>
	// 导入store中购物车模块
	import {mapState,mapMutations} from 'vuex'
	export default {
		computed:{
			...mapState('m_cart',['cart'])
		},
		data() {
			return {
			    ...
			};
		},
		methods:{
			...mapMutations('m_cart',['addToCart']),
			async getGoodDetail(goodId){
			    ...
			},
			// 跳转到购物车页面
			onClick(e){
			    ...
			},
			// 添加到购物车
			buttonClick(e){
				if(e.content.text==='加入购物车'){
					// 定义新商品信息
					const goods={
						goods_id:this.goodInfo.goods_id,
						goods_name:this.goodInfo.goods_name,
						goods_price:this.goodInfo.goods_price,
						goods_count:1,
						goods_small_logo:this.goodInfo.goods_small_logo,
						goods_state:true
					}
					this.addToCart(goods)
				}
			}
		},
		onLoad(){
			this.getGoodDetail()
		}
	}
</script>
```
此时点击购物车按钮，控制台打印出来的goods变量就是我们刚才添加的商品信息。

## 9.4 动态统计购物车中的商品总数量
思路：
把动态获取的购物车中商品的数量赋值到options配置项的info上面。
- cart.js添加getters方法，统计数量

```
getters:{
	total(state){
			let count=0;//定义初识的总数量
			state.cart.forEach((item)=>{
				count+=item.goods_count;	
			})
			return count;
	}
}
```
- goods-detail页面导入并映射getters中的方法

```
    import {mapState,mapMutations,mapGetters} from 'vuex'
	export default {
		computed:{
			...mapState('m_cart',['cart']),
			...mapGetters('m_cart',['total'])
		},
		data() {
		    。。。
		}
	}
```
- 定义监听器把新值赋值给info变量

```
export default {
	computed:{
		。。。
	},
	// 监听器 监听新值赋值给info
	watch:{
		total(newValue){
			const findResult=this.options.find(item=>item.text==="购物车")
			if(findResult){
				findResult.info=newValue	
			}
		}
	},
	。。。
}
```
- 初始化原来options中info为0
![1.png](https://note.youdao.com/yws/res/6103/WEBRESOURCEc801d2df3d67c04e1924d6a72dcd8518)

此时我们添加到购物车，购物车中商品的数量就会增加。
![01.gif](https://note.youdao.com/yws/res/6161/WEBRESOURCEf5fd2118c769ad34f671d198204ad94f)

## 9.5 持久保存购物车数量

我们前面实现的步骤，如果刷新页面，购物车的数量又会恢复到初识的数值0，所以我们需要持久化保存数据。

- cart.js定义方法保存购物车数据cart。


```
mutations:{
		// 定义添加到购物车方法
		addToCart(state,goods){
			。。。
		},
		// 定义方法把数据保存到本地存储
		saveToStorage(state){
			uni.setStorageSync('cart',JSON.stringify(state.cart))
		}
	},
```


- cart.js中在调用addToCart方法的时候保存数据

```
mutations:{
		// 定义添加到购物车方法
		addToCart(state,goods){
		    。。。。
			// 调用持久保存的方法
			this.commit('m_cart/saveToStorage')
		},
		// 定义方法把数据保存到本地存储
		saveToStorage(state){
			uni.setStorageSync('cart',JSON.stringify(state.cart))
		}
	},
```
- cart.js中cart数值刚开始应该是从缓存中读取数据并赋值

```
    state:()=>({
		cart:JSON.parse(uni.getStorageSync('cart')||'[]')
	}),
```
此时再点击添加到购物车，storage的缓存中就能看到数据了。

## 9.6页面加载就显示购物车数据

我们的代码在点击小程序的编译以后，也就是页面第一次进来以后，购物车的数量是空的，这个不合理，比如我选过商品了，然后我再一次进入页面，此时应该是我选过的商品数量。
我们修改一下我们自己定义的total监听器，最好是页面一加载进来就立即调用。
![1.png](https://note.youdao.com/yws/res/6129/WEBRESOURCE93012ae1d0d36dd4d6322dbcb420466f)

所以我们修改监听器的代码为：

```
watch:{
	// 页面一加载进来就立即调用的写法
	total:{
		handler:function(newValue){
			const findResult=this.options.find(item=>item.text==="购物车")
			if(findResult){
				findResult.info=newValue	
			}
		},
		immediate:true
	}
}
```
此时小程序模拟器点击编译也能正常显示你添加过的数据。

## 9.7 购物车页面同步选中的数据

请查看uniapp官网的具体使用说明：
![1.png](https://note.youdao.com/yws/res/6127/WEBRESOURCE1c25d385366b4fb5fe6097a3aa365b91)

所以我们在pages/shop页面添加代码如下：

```
<script>
	import {mapGetters} from 'vuex'
	export default {
		computed:{
			...mapGetters('m_cart',['total'])
		},
		onShow(){
			// 页面一显示的时候就调用的方法
			this.setBadge()
		},
		methods:{
			setBadge(){
				uni.setTabBarBadge({
					index:2,
					// 因为text的赋值必须是字符串,所以添加空字符串
					text:this.total+''
				})
			}
		}
	}
</script>
```
![01.gif](https://note.youdao.com/yws/res/6074/WEBRESOURCE67393277aae1995b0b8b8c16be127fe3)

## 9.8 复用设置购物车徽标代码

mixins就是定义一部分公共的方法或者计算属性,然后混入到各个组件中使用,方便管理与统一修改。

所以我们在项目的根目录创建mixins文件夹，里面新建setBadge.js文件，内容如下：
![2.png](https://note.youdao.com/yws/res/6066/WEBRESOURCEca8fdb8d0e4fbc0bb253fa08ea989477)

然后在tabBar的首页、分类页、购物车页和我的页面都可以如下引入并使用，
比如我在cate.vue页面添加如下：

```
<script>
	// 引入设置徽标的公共计算属性
	import setBadge from '@/mixins/setBadge.js'
	export default {
		mixins:[setBadge],
		data() {
			...
		},
		...
	}
</script>
```
其他页面一样。

# 十、购物车页面

## 10.1 商品列表数据展示

在shop页面导入cart.js中的cart数组并循环使用，因为和subpkg里面的good-list页面结构十分相似，我们把那个页面的结构和样式复制过来即可，也可以自己封装成组件调用。

```
<template>
	<view>
		<!-- 购物车标题部分 -->
		<view class="cart-slogan">
			<uni-icons type="shop" size="20"></uni-icons>
			<text>军校广场惠友超市</text>
			<uni-tag text="标签" type="success"></uni-tag>
			<uni-tag text="标签" type="warning"></uni-tag>
		</view>
		<!-- 购物车数据列表部分 -->
		<view class="goods-list">
				<view class="goods-item" v-for="(goodItem,goodIndex) in cart" :key="goodIndex">
					<image :src="goodItem.goods_small_logo" class="goods-pic"></image>
					<view class="goods-info">
						<view>{{goodItem.goods_name}}</view>
						<view class="price">{{goodItem.goods_price|handlePrice}}</view>
					</view>
				</view>
		</view>
	</view>
</template>

<script>
	// 导入cart.js中的数据
	import {mapState,mapGetters} from 'vuex'
	export default {
		computed:{
			...mapState('m_cart',['cart']),
			...mapGetters('m_cart',['total'])
		},
		// 定义处理商品价格的过滤器
		filters:{
			handlePrice:function(num){
				return '¥'+num.toFixed(1)
			}
		},
		onShow(){
			// 页面一显示的时候就调用的方法
			this.setBadge()
		},
		methods:{
			setBadge(){
				uni.setTabBarBadge({
					index:2,
					// 因为text的赋值必须是字符串,所以添加空字符串
					text:this.total+''
				})
			}
		}
	}
</script>

<style lang="scss">
.cart-slogan{
	width:100%;
	height:80rpx;
	display: flex;
	justify-content: flex-start;
	align-items: center;
	text{
		margin:0 10rpx;
	}
}	
.goods-list{
	.goods-item{
		width:100%;
		height:220rpx;
		margin-bottom:10rpx;
		display: flex;
		border-bottom:1px solid #f0f0f0;
		.goods-pic{
			display: block;
			width:200rpx;
			height:200rpx;
			margin-right:10rpx;
		}
		.goods-info{
			flex:1;
			display: flex;
			flex-direction: column;
			justify-content: space-around;
			.price{
				color:#FF5A5F;
			}
		}
		
	}
}
</style>

```
我们的页面此时只会显示一个商品的内容，因为我们的接口原因，我们商品详情只模拟的一个商品数据。

如果替换成真正后台写的接口就没有问题了。

![1.png](https://note.youdao.com/yws/res/6148/WEBRESOURCE960b1f701ad6c1df92b411e1763e346f)

## 10.2 添加左侧单选框和右侧数量板块

uniapp中提供了单选框的用法，我们读取文档复制使用即可。
结构如下：

```
<!-- 购物车数据列表部分 -->
		<view class="goods-list">
				<view class="goods-item" v-for="(goodItem,goodIndex) in cart" :key="goodIndex">
					<view class="goods-left">
						<radio class="good-check"/>
						<image :src="goodItem.goods_small_logo" class="goods-pic"></image>
					</view>
					<view class="goods-info">
						<view>{{goodItem.goods_name}}</view>
						<view class="price">{{goodItem.goods_price|handlePrice}}</view> 
					</view>
				</view>
		</view>
```
样式如下：

```
.goods-list{
	.goods-item{
		width:100%;
		height:220rpx;
		margin-bottom:10rpx;
		display: flex;
		border-bottom:1px solid #f0f0f0;
		.goods-left{
			width:240rpx;
			height:220rpx;
			display: flex;
			justify-content: space-around;
			align-items: center;
			.goods-pic{
				display: block;
				width:200rpx;
				height:200rpx;
				margin-right:10rpx;
			}
		}
		.goods-info{
			flex:1;
			display: flex;
			flex-direction: column;
			justify-content: space-around;
			.price{
				color:#FF5A5F;
			}
		}
		
	}
}
```
## 10.3 单选按钮动态切换状态

- 单击事件的时候保存商品更改后的状态

```
  <radio class="good-check" :checked="goodItem.goods_state" @click="radioHandle(goodItem)"/>    
 
 下面定义方法如下：
 
 // 单选框的单击事件
methods:{
    。。。，
	// 单选框的单击事件
	radioHandle(item){
		let obj={
			goods_id:item.goods_id,
			goods_state:!item.goods_state
		}
	}
}
```

- store/cart.js中定义更新状态的方法


```
mutations:{
    // 定义方法把数据保存到本地存储
		saveToStorage(state){
			uni.setStorageSync('cart',JSON.stringify(state.cart))
		},
		// 定义更新商品选中状态的方法
		updateState(state,goods){
			// 先查找用户要编辑的当前用户信息状态
			let findResult=state.cart.find(item=>item.goods_id===goods.goods_id)
			if(findResult){
				findResult.goods_state=goods.goods_state;
				// 更新后调用持久保存的方法
				this.commit('m_cart/saveToStorage')
			}
			
		}
}
```
- shop.vue页面导入定义的updateState并不更新后的对象传递过去

```
<script>
	// 导入cart.js中的数据
	import {mapState,mapGetters,mapMutations} from 'vuex'
	export default {
		methods:{
			...mapMutations('m_cart',['updateState']),
			// 单选框的单击事件
			radioHandle(item){
				let obj={
					goods_id:item.goods_id,
					goods_state:!item.goods_state
				}
				this.updateState(obj)
			}
		}
	}
</script>
```
此时显示效果如下：
![01.gif](https://note.youdao.com/yws/res/6101/WEBRESOURCEd31f4c3297e2f8d76c99d22ff8d38ba8)

## 10.4 数字输入框

我们一般在购物车页面的增加和减少数量的框使用下面的ui组件，具体使用方法请参照文档

![5.png](https://note.youdao.com/yws/res/6110/WEBRESOURCE23f4add7d396ffe437e0873f8a328e4f)

我们粘贴过来可能有的样式不显示，因为整个页面背景色是灰色的，我们把.goods-list设置白色背景色就能看出来了。

结构如下：

```
<view class="goods-info">
	<view>{{goodItem.goods_name}}</view>
		<view class="price">
            <view>{{goodItem.goods_price|handlePrice}}</view>
				<uni-number-box  class="goods-mange" :min="0" :value="goodItem.goods_count"></uni-number-box>
			</view> 
        </view>
    </view>
</view>
```
![1.png](https://note.youdao.com/yws/res/6092/WEBRESOURCE7572661ee2aaea8bde8face873235dd7)

## 10.5 监听商品数量变化

- 给uni-number-box绑定change事件

```
<uni-number-box :min="0" :value="goodItem.goods_count" @change="changeHandle"></uni-number-box>
```
- 事件函数中把更改后的新数量获取并传递



```
methods:{
    changeHandle(e){
		// e是用户点击加减或者在输入框输入内容的时候获取的值  
		let obj={
			goods_id:23,
			goods_count:e
		}
		this.updateGoodsNum(obj)
	}
}
```
- store/cart.js中定义updateGoods这个更新方法

```
// 更新购物车中商品的数量
updateGoodsNum(state,goods){
	let findResult=state.cart.find(item=>item.goods_id===goods.goods_id);
	if(findResult){
		findResult.goods_count=goods.goods_count;
		// 更新后调用持久保存的方法
		this.commit('m_cart/saveToStorage')
	}
}
```
- 购物车页面得引入并调用updateGoodsNum方法

```
    import {mapState,mapGetters,mapMutations} from 'vuex'
	export default {
		methods:{
			...mapMutations('m_cart',['updateState','updateGoodsNum']),
            。。。
			changeHandle(e){
			
				let obj={
					goods_id:23,
					goods_count:e
				}
				this.updateGoodsNum(obj)
				//重新调用一次setBadge
				this.setBadge()
			}
		}
	}
```
上面我们不能把goods_id写成固定值，所以可以再uni-number-box外面包裹一个view,给它绑定单击事件，然后把商品的goods_id保存起来，changeHandle方法就能使用了。

- uni-number-box外部嵌套view绑定单击事件

```
<view @click="saveGoodId(cartItem)">
	<uni-number-box :min="0" :value="cartItem.goods_count"  @change="changeHandle"></uni-number-box>
</view>	
```
- saveGoodId方法如下：

```

	export default {
		data() {
			return {
			  // 初始化商品goods_id
			    goodId:0
			}
		},
	    methods:{
			...
			saveGoodId(cartItem){
				this.goodId=cartItem.goods_id
		}
	}
```
- 上面的changeHandle方法更改如下：

```
	export default {
		methods:{
			...mapMutations('m_cart',['updateState','updateGoodsNum']),
            。。。
			changeHandle(e){
			
				let obj={
					goods_id:this.goodId,
					goods_count:e
				}
				this.updateGoodsNum(obj)
				//重新调用一次setBadge
				this.setBadge()
			}
		}
	}
```

## 10.6 实现单项滑动删除效果

我们在购物车页面添加uni-swipe-action标签，具体使用参照文档

- 购物车页面的结构如下：
![1.png](https://note.youdao.com/yws/res/6158/WEBRESOURCE0227d87d6d5469ea8e38faf55dfd9d5f)

- data中添加options配置项

```
data() {
	return {
		options:[
			{
				text: '删除',
				style: {
					backgroundColor: '#dd524d'
				},
							
			}
		]
	};
}
```
- 实现删除功能

在store/cart.js中定义一个删除的方法

```
mutations:{
    // 删除购物车中的商品
		delGoodsHandle(state,goods){
			let index=state.cart.findIndex(item=>item.goods_id===goods.goods_id)
			state.cart.splice(index,1)
			// 更新后调用持久保存的方法
			this.commit('m_cart/saveToStorage')
		}
}
```
在shop.vue页面导入并使用这个方法

```
<script>
	// 导入cart.js中的数据
	import {mapState,mapGetters,mapMutations} from 'vuex'
	export default {
		methods:{
			...mapMutations('m_cart',['updateState','updateGoodsNum','delGoodsHandle']),
			。。。
			// 删除购物车中的商品
			delGood(goods){
				this.delGoodsHandle(goods)
			}
		},
		。。。
	}
</script>
```

当然最主要的是你上面uni-swipe-action得绑定单击事件，而且刚开始拿不到商品信息，需要把页面结构也更改下。
![22.png](https://note.youdao.com/yws/res/6071/WEBRESOURCE855ff42c89d32f563ddbfa7d2ba72b74)

# 十一、收货地址管理

## 11.1 创建收货地址组件

- 创建my-address组件，注意不能叫address,好像是关键字，不显示

![11.png](https://note.youdao.com/yws/res/6135/WEBRESOURCE79cc77445cb0152b1c719831c871db0d)

my-address中随意写点内容


- 需要的页面引入（shop.vue）

```
<!-- 使用搜索组件 -->
<my-address></my-address>
```
上面购物车页面顶部能显示收货地址代表组件创建没有问题。


## 11.2 完善收货地址结构渲染

- 渲染页面结构
```
<template>
	<view class="add-address">
		<!-- 添加收货地址按钮 -->
		<view class="btn-box">
			<button class="mini-btn" type="primary" size="mini">请选择收货地址</button>
		</view>
		<!-- 收货人的详细信息 -->
		<view class="address-info">
			<view class="username-info">
				<view>
					<text>收货人：</text>
					<text>张三</text>
				</view>
				<uni-icons type="right" size="20"></uni-icons>
			</view>
			<view class="phone-info">
				<text>联系电话：</text><text>13245678902</text>
			</view>
			<view class="address-detail">
				<text>详细地址：</text>
				<text>河北省保定市河北省保定市河北省保定市河北省保定市河北省保定市河北省保定市河北省保定市河北省保定市河北省保定市</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name:"address",
		data() {
			return {
			
			};
		}
	}
</script>

<style lang="scss">
.add-address{
	width:100%;
	background-color: #fff;
	border-bottom:1px solid #DEDEDE;
	.btn-box{
		height:80rpx;
		display: flex;
		justify-content: space-around;
		align-items: center;
	}
}
.address-info{
	font-size:14px;
	.username-info{
		width:100%;
		height:50rpx;
		display: flex;
		justify-content: space-between;
		align-items: center;	
	}
	.phone-info{
		height:50rpx;
		line-height: 50rpx;
	}
}

</style>

```
- 添加地址按钮和地址具体信息板块按需显示
现在data中定义一个空对象，代表详细地址信息对象

```
data() {
	return {
		address:{}
	};
}
```
然后页面结构添加v-if和v-else

```
<template>
	<view class="add-address">
		<!-- 添加收货地址按钮 -->
		<view class="btn-box" v-if="JSON.stringify(address)==='{}'">
		    ...
		</view>
		<!-- 收货人的详细信息 -->
		<view class="address-info" v-else>
			...
		</view>
	</view>
</template>

<script>
	export default {
		name:"address",
		data() {
			return {
				address:{
				}
			};
		}
	}
</script>


```

## 11.3 选择收获地址
我们点击选择用户地址按钮应该是调用uni.chooseAddress方法，获取用户的地址，返回值是promise对象。

**注意**
uni.chooseAddress()方法在模拟器拿不到真实地址，是假地址，你可以如下操作，在真机上面测试查看。

- 1、下面是在你的手机上查看你自己写的项目的真机效果
![1.png](https://note.youdao.com/yws/res/6116/WEBRESOURCEeb0b4f1cbfede59434beb93db917ab8c)

- 2、如果你想模拟在真机上拿到的数据和调试，请如下操作
![2.png](https://note.youdao.com/yws/res/6126/WEBRESOURCEcfac2a41b62ffac3c533e47fe7cf9325)

扫描上面的二维码可以查看打印的数据

注意先扫步骤1，再扫步骤2，有的时候网络不稳定，好多情况会返回错误信息，有的时候会成功，所以我们的代码需要捕获错误并判断。

如果是错误信息返回如下：
![111.png](https://note.youdao.com/yws/res/6114/WEBRESOURCE4da66827be611d9ec441ae1a81237ebf)

如果是正确信息返回如下：
![1.png](https://note.youdao.com/yws/res/6104/WEBRESOURCEfde8ad868f0abf0ba977c99706c63da0)

所以my-address组件结构如下：

```
<template>
	<view class="add-address">
		<!-- 添加收货地址按钮 -->
		<view class="btn-box" v-if="JSON.stringify(address)==='{}'">
			<button class="mini-btn" type="primary" size="mini" @click="chooseAddress">请选择收货地址</button>
		</view>
		<!-- 收货人的详细信息 -->
		<view class="address-info" v-else>
			<view class="username-info">
				<view>
					<text>收货人：</text>
					<text>{{address.userName}}</text>
				</view>
				<uni-icons type="right" size="20"></uni-icons>
			</view>
			<view class="phone-info">
				<text>联系电话：</text><text>{{address.telNumber}}2</text>
			</view>
			<view class="address-detail">
				<text>详细地址：</text>
				<text>{{addressJoin}}</text>
			</view>
		</view>
	</view>
</template>
```
数据如下：

```
export default {
		name:"address",
		data() {
			return {
				address:{
				}
			};
		},
		methods:{
			async chooseAddress(){
				const [err,success]=await uni.chooseAddress().catch(err=>err)
				if(err===null&&success.errMsg==="chooseAddress:ok"){
					this.address=success
				}
				
			}
		},
		// 计算属性,拼接地址
		computed:{
			addressJoin(){
				if(this.address.provinceName=='')return ''
				return this.address.provinceName+this.address.cityName+this.address.countyName+this.address.detailInfo
			}
		}
	}
```
此时演示效果如下（真机上会看到你的真实地址，下面动图是模拟器的地址）：
![01.gif](https://note.youdao.com/yws/res/6107/WEBRESOURCE8b1e9a38560a82b1ba2c7a627514ed9f)

## 11.4 用户的收货地址存储到vuex中

- store文件夹下面新建user.js，内容如下：

```
export default{
	// 开启命名空间
	namespaced:true,
	state:()=>({
		address:{}
	}),
	mutations:{
		// 定义添加到购物车方法
		updateAddress(state,address){
			state.address=address
		}
	},
	getters:{
		
	}
}
```
- store文件夹下面的store.js导致user模块，代码如下：

```
import Vue from 'vue'
import Vuex from 'vuex'
// 导入购物车模块
import moduleCart from '@/store/cart.js'
// 导入用户模块
import moduleUser from '@/store/user.js'
Vue.use(Vuex)
const store=new Vuex.Store({
	modules:{
		'm_cart':moduleCart,
		'm_user':moduleUser,
	}
})
export default store;
```
- my-address组件使用store中的address对象和updateAddress方法，具体代码如下：
![11.png](https://note.youdao.com/yws/res/6064/WEBRESOURCE6f9fa71f17d362ff0189dc7287449001)

## 11.5持久化保存address

修改store/user.js的内容如下：
![2.png](https://note.youdao.com/yws/res/6095/WEBRESOURCE1d29450cd1143b88f6f8fb576d9c34d3)

## 11.5 复用地址的计算属性

- 我们把my-address组件中的计算属性addressJoin抽离放到store/user.js的getters中去。

```
getters:{
		// 动态拼接地址
		addressJoin(state){
			if(state.address.provinceName=='') return ''
			return state.address.provinceName+state.address.cityName+state.address.countyName+state.address.detailInfo
		}
	}
```
- my-address组件中导入mapGetters

```
import {mapState,mapMutations,mapGetters} from 'vuex'
```
- my-address组件计算属性中使用

```
computed:{
	...mapState('m_user',['address']),
	...mapGetters('m_user',['addressJoin'])
			
}
```
此时访问数据都正常就没有问题

- 允许用户重新选择收获地址
我们把地址区域绑定上面的chooseAddress方法，就能重新读取地址信息并确认
![1.png](https://note.youdao.com/yws/res/6078/WEBRESOURCE711dfb48e5209a3eb28114bbca12f325)

## 11.6 用于授权处理收货地址

真机在进入这个收货地址板块的时候，需要用户的授权，如果用户选择确定能正常获取用户信息，如果点击取消就不能获取用户的地址信息。

所以我们避免用户不小心选了取消出问题，我们可以如下操作：

```
methods:{
			...mapMutations('m_user',['updateAddress']),
			async chooseAddress(){
				const [err,success]=await uni.chooseAddress().catch(err=>err)
				if(err===null&&success.errMsg==="chooseAddress:ok"){
					// this.address=success
					// console.log(address)
					this.updateAddress(success)
				}
				// 如果用户单击取消授权了,我们让他重新授权
				if(err&&(err.errMsg==="chooseAddress:fail auth deny"||err.errMsg==='chooseAddress:fail authorize no response')){
					this.reAuth()
				}
			},
			// 重新授权方法
			async reAuth(){
				const [err,confirmRresult]=await uni.showModal({
					content:'您没有授权，请授权',
					confirmText:'确认',
					cancleText:'取消'
				})
				if(err) return 
				if(confirmRresult.cancle) return uni.$showMsg('您取消了授权')
				if(confirmRresult.confirm) return uni.openSetting({
					success:(settingResult)=>{
					    if(settingResult.authSetting['scope.address']){
							return uni.$showMsg('授权成功，请选择地址！')
						}
						if(!settingResult.authSetting['scope.address']){
							return uni.$showMsg('您取消了地址授权！')
						}
					}
				})
			}
		}
```
# 十二、结算功能

## 12.1 自定义组件

- components下面创建自定义组件my-settle，里面内容和样式如下：

```
<template>
	<view class="settle-container">
		结算区域
	</view>
</template>

<style lang="scss">
.settle-container{
	width: 100%;
	height:80rpx;
	background-color: pink;
	position: fixed;
	left:0;
	bottom:0;
}
</style>
```
- shop页面底部引入

```
<!-- 添加结算组件 -->
<my-settle></my-settle>
```
- 放在结算组件覆盖页面内容，给shop页面添加底部内padding为结算组件的高度

shop页面的根标签命名为shop-container

```
.shop-container{
	padding-bottom:80rpx;
}
```
## 12.2 结算区结构渲染

```
<template>
	<view class="settle-container">
		<label for="">
			<radio class="good-check"/> 
		</label>
		<!-- 总计 -->
		 <view class="total-count">
			 总计：<text>&yen;123.00</text>
		 </view> 
		<!-- 计算按钮 -->
		<view class="count-btn">
			计算总价(5)
		</view>
	</view>
</template>

<style lang="scss">
.settle-container{
	width: 100%;
	height:80rpx;
	background-color: pink;
	position: fixed;
	left:0;
	bottom:0;
	display: flex;
	justify-content: space-between;
	align-items: center;
	padding:0 10rpx;
	box-sizing: border-box;
	.count-btn{
		width:200rpx;
		min-width: 200rpx;
		height:60rpx;
		background-color: #e1251b;
		border-radius: 30rpx;
		font-size:28rpx;
		color:#fff;
		text-align: center;
		line-height: 60rpx;
	}
}
</style>

```
显示如下：
![1.png](https://note.youdao.com/yws/res/6079/WEBRESOURCEbdc20c5c5658d1362bde24e6330d9669)

## 12.3 动态计算数值

- 我们需要计算出用户选中的商品的总数量，所以在store/cart.js中定义一个监听方法

```
	getters:{
	    。。。
		// 动态计算选中商品的总件数
		checkedCount(state){
			return state.cart.filter(a=>a.goods_state).reduce((total,item)=>{
				return total+=item.goods_count
			},0)
		}
	}
```
- my-settle中引入并使用

```
<template>
	<view class="settle-container">
	    。。。
		<view class="count-btn">
			计算总价{{checkedCount}}
		</view>
	</view>
</template>

<script>
	import {mapGetters} from 'vuex'
	export default {
		name:"my-settle",
		。。。
		computed:{
			...mapGetters('m_cart',['checkedCount'])
		}
	}
</script>
```
此时用户选中多少件商品，总计里就会显示多少件商品。

## 12.4 动态渲染全选按钮是否选中
- my-settle.vue中代码如下：

```
<template>
	<view class="settle-container">
		<label for="">
			<radio class="good-check":checked="isFullCheck"/> 
		</label>
		<!-- 总计 -->
		。。。
		<!-- 计算按钮 -->
		<view class="count-btn">
			计算总价{{checkedCount}}
		</view>
	</view>
</template>

<script>
	import {mapGetters} from 'vuex'
	export default {
		name:"my-settle",
		computed:{
			...mapGetters('m_cart',['checkedCount','total']),
			// 判断购物车中总数量和用户选中的总数量是否相等
			isFullCheck(){
				return this.total===this.checkedCount
			}
		}
	}
</script>
```
- 需要注意的是你的store/cart.js中得有total和checkedCount两个监听计算方法。（getters里面）

## 12.5 全选按钮控制上面的小复选框状态

- store/cart.js中定义方法更新复选框状态

```
	mutations:{
	    。。。
		// 更新小复选框状态
		updateAllCheck(state,newState){
			state.cart.forEach(item=>{
				item.goods_state=newState
			})
			// 持久化保存更新状态
			this.commit('m_cart/saveToStorage')
		}
		
	}
```
- my-settle页面添加如下：

```
<template>
	<view class="settle-container">
		<label for="" @click="changeAll">
			<radio class="good-check":checked="isFullCheck"/> 
		</label>
		<!-- 总计 -->
		。。。
	</view>
</template>

<script>
	import {mapGetters,mapMutations} from 'vuex'
	export default {
		name:"my-settle",
		computed:{
			...mapGetters('m_cart',['checkedCount','total']),
			// 判断购物车中总数量和用户选中的总数量是否相等
			isFullCheck(){
				return this.total===this.checkedCount
			}
		},
		methods:{
			...mapMutations('m_cart',['updateAllCheck']),
			changeAll(){
				this.updateAllCheck(!this.isFullCheck)
			}
		}
	}
</script>
```
此时点击底部的全选按钮，上面的小复选框全部选中，点击底部的全选按钮取消选中，上面的小复选框全部取消选中。

## 12.6动态渲染已勾选商品的总价格

- store/cart.js中定义getters中的一个监听方法，动态计算选中的商品的总价格，代码如下：

```
getters:{
    // 动态计算选中商品的总价格
	checkedTotalPrice(state){
		return state.cart.filter(item=>item.goods_state).reduce((total,item)=>total+=item.goods_count*item.goods_price,0).toFixed(2)
}
```
- my-settle页面引入并使用
![1.png](https://note.youdao.com/yws/res/6093/WEBRESOURCE7cfc72d4b0f77f96a83cd0a205642c49)

**注意**

我们计算总价的时候如果出问题，请把你的商品购物车列表展示的时候那个单价原来数据是23.56，当时演示的时候添加了一个过滤器，注意过滤器里面不要调用toFixed方法去过滤数据的小数点，不然总价出来就会有偏差。

## 12.7更新徽标数值

就是我们点击购物车数量的时候，总数量会更新，但是徽标中的数量不会更新
![2.png](https://note.youdao.com/yws/res/6075/WEBRESOURCE65ca9463e625761510d2759710bc1ece)

我们在mixins/setBadge.js中定义监听方法如下：

```
watch:{
	total(){
		this.setBadge()
	}
}
```
**注意**
只要total的数值发生变化，就重新调用setBadge方法，给tabBar中徽标赋值。


```
<template>
	<view class="shop-container" v-if="cart.length!==0">
		...
	</view>
	<!-- 空白购物车结构 -->
	<view class="empty-container" v-else>
		<img src="https://oss.suning.com/vss/activity/wximg/cart/sn-cart-empty.png" alt="">
		<text>购物车还是空的，快来挑选好货吧</text>
	</view>
</template>
```
样式如下：

```
.empty-container{
	width:100%;
	padding-top:300rpx;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	img{
		width:200rpx;
		height:200rpx;
	}
	text{
		font-size:28rpx;
		margin-top:20rpx;
	}
}
```
显示如下：
![1.png](https://note.youdao.com/yws/res/6155/WEBRESOURCE9a3004b52fcb0f11e48bbb36640a0781)

**补充**

如果单件商品的数量小于0在购物车的列表中也就不应该存在了，所以添加如下;

```
<view class="cart-item" v-for="(cartItem,cartIndex) in cart" :key="cartIndex" v-if="cartItem.goods_count>0">
  .....
</view>
```

## 12.8 git提交

先保证在cart分支上面
1. git add .
2. git commit -m '完成了购物车功能'
3. git push -u origin cart 远程创建cart分支
4. git checkout master  切换到主分支
5. git merge cart  合并购物车分支
6. git push 本地master推送到远程master
7. git branch -d cart 删除cart分支（这步可以操作也可以不操作）

# 十三、登录功能和支付功能

## 13.1创建分支

```
git checkout -b pay
```
## 13.2 点击计算按钮逻辑

点击计算按钮之前，先判断用户是否勾选了商品、用户是否选择了配送地址、用户是否已经登录，所以我们如下操作。

- 给计算按钮绑定事件

```
<!-- 计算按钮 -->
	<view class="count-btn" @click="countTotal">
		计算总价{{checkedCount}}
	</view>
```
- store/user.js中暂时定义token为空

```
state:()=>({
		address:JSON.parse(uni.getStorageSync('address')||'{}'),
		token:''
	})
```

- my-settle.vue页面引入并判断

```
<script>
	import {mapState,mapGetters,mapMutations} from 'vuex'
	export default {
		name:"my-settle",
		computed:{
			...mapGetters('m_cart',['checkedCount','total','checkedTotalPrice']),
			...mapGetters('m_user',['addressJoin']),
			...mapState('m_user',['token']),
		    。。。
		},
		methods:{
			...mapMutations('m_cart',['updateAllCheck']),
			changeAll(){
			  。。。
			},
			// 计算总价方法
			countTotal(){
				// 如果商品没有选择不允许点击计算按钮
				if(!this.checkedCount) return uni.showToast({title:'请先选择商品!'})
				// 如果用户没有选择地址,不允许点击计算按钮
				if(!this.addressJoin) return uni.showToast({title:'请选择商品地址!'})
				// 如果用户没有登录,就不能点击计算按钮
				if(!this.token) return uni.showToast({title:'请先登录'})
				
			}
		}
	}
</script>
```
## 13.3 我的个人中心页面

### 13.3.1 登录组件和个人中心组件按需显示

- components下面新建my-login和my-userInfo两个组件
- 在个人中心页面my.vue页面导入两个组件

```
<my-login v-if="!token"></my-login>
<my-userInfo v-else></my-userInfo>
```
- my页面引入store/user.js中的token并做为判断按需展示的条件

```
<template>
	<view>
		<my-login v-if="!token"></my-login>
		<my-userInfo v-else></my-userInfo>
	</view>
</template>

<script>
	import {mapState} from 'vuex'
	export default {
		data() {
			return {
				
			};
		},
		computed:{
			...mapState('m_user',['token'])
		}
	}
</script>
```
### 13.3.2登录组件结构和样式渲染
![1.png](https://note.youdao.com/yws/res/6123/WEBRESOURCE784340068ecfa38655f73a6e659966c2)

在my-login组件中实现下面的代码：

```
<template>
	<view class="login-container">
		<uni-icons type="contact-filled" size="100" color="#AFAFAF"></uni-icons>
		<button type="primary" class="login-btn" open-type="getUserInfo" @getuserinfo="getUserInfo">一键登录</button>
		<text class="login-tips">登录后可以享受多种优惠政策</text>
	</view>
</template>

<style lang="scss">
.login-container{
	width:100%;
	height:800rpx;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	.login-btn{
		width:90%;
		height:80rpx;
		background-color: #fc0;
		border-radius: 80rpx;
		margin:20rpx 0;
		border:0;
		color:#222;
	}
}
</style>
```

### 13.3.3把用户头像信息存储到vuex

- store/user.js中定义userInfo对象

```
state:()=>({
	address:JSON.parse(uni.getStorageSync('address')||'{}'),
	token:'',
	// 定义用户信息对象
	userInfo:JSON.parse(uni.getStorageSync('userInfo')||'{}')
})
```

- mutaions中定义两个方法，一个是更新用户信息对象，一个是持久化保存

```
mutations:{
	。。。
	// 更新用户信息对象的方法
	updateUserInfo(state,userInfo){
		state.userInfo=userInfo
		// 调用持久化保存信息对象的方法
		this.commit('m_user/saveStorageUserInfo')
	},
	// 持久化保存用户信息方法
	saveStorageUserInfo(state){
		uni.setStorageSync('userInfo',JSON.stringify(state.userInfo))
	}
}
```
- my-login.vue组件引入并使用

```
<script>
	import {mapMutations} from 'vuex'
	export default {
	    。。。
		methods:{
			...mapMutations('m_user',['updateUserInfo']),
			getUserInfo(e){
				if(e.detail.errMsg==='getUserInfo:fail auth deny') return uni.showToast({
					'title':'您取消了授权',
					 duration: 2000
				})
				// 如果获取用户信息成功就保存到store中
				this.updateUserInfo(e.detail.userInfo)
			}
		}
	}
</script>
```
此时点击登录按钮会把获取到的用户信息保存到本地存储里面。

### 13.3.4 实现登录功能


#### （1）获取token
登录接口调用的时候需要传递给后端四个参数，后端返回给我们token字符串，我们携带token才能去做其他的处理。
1. code:用户登录的凭证
2. encrytedData 完整用户信息密文
3. iv 加密算法的初始量
4. rawData 用户信息原始数据字符串
5. signature 使用sha1得到的字符串

需要注意的是我是模拟的后端接口（token的格式可能不是很正确，这个无所谓，就是知道后端必须返回给我们token才可以），地址如下：

```
https://www.fastmock.site/mock/6c3454cb9716e486ccedb6060afe9551/shop/login
```

我们访问的时候直接写/login就行，因为我们前面设置过接口的请求基数地址。

修改m-login.vue组件中的getUserInfo方法

```
methods:{
			...mapMutations('m_user',['updateUserInfo']),
			getUserInfo(e){
				if(e.detail.errMsg==='getUserInfo:fail auth deny') return uni.showToast({
					'title':'您取消了授权',
					 duration: 2000
				})
				// 如果获取用户信息成功就保存到store中
				this.updateUserInfo(e.detail.userInfo)
				// 调用自己定义的登录方法
				this.getToken(e.detail)
			},
			// 实现处理登录的方法
			async getToken(info){
				const [err,res]=await uni.login().catch(err=>err);
				// 添加err||的目的是万一连err对象都不存在 也判断这种情况
				if(err||res.errMsg!=='login:ok') return uni.showToast({
					title:'登录失败',
					duration:2000
				})
				console.log(info)
				const query={
					encryptedData:info.encryptedData,
					iv:info.iv,
					rawData:info.rawData,
					signature:info.signature,
					code:res.code
				}
				// 调用后端接口,我们是模拟的
				const result=await uni.$http.post('/login',query);
				const {data,status}=result.data
				if(status!==200) return uni.showToast({
					title:'登录失败',
					duration:2000
				})
				uni.showToast({
					title:'登录成功',
					duration:2000
				})
				console.log(data)
			
			}
		}
```

#### (2) 把得到的token存储到vuex中

- store/use.js定义更新token的方法

```
mutations:{
		。。。
		// 定义更新保存token的方法
		updateToken(state,token){
			state.token=token;
			// 调用持久化保存token的方法
			this.commit('m_user/saveStorageToken')
		},
		// 持久化保存token方法
		saveStorageToken(state){
			uni.setStorageSync('token',state.token)
		}
	},
```

- store/use.js的state中的token就应该从缓存中获取token,更改如下：

```
state:()=>({
		address:JSON.parse(uni.getStorageSync('address')||'{}'),
		token:uni.getStorageSync('token')||'',
		// 定义用户信息对象
		userInfo:JSON.parse(uni.getStorageSync('userInfo')||'{}')
	}),
```
- my-login.vue组件导入updateToken方法并把登录成功后的token传递过去

![11.png](https://note.youdao.com/yws/res/6140/WEBRESOURCEbb8407cf9b99d65f6dd385297ba9c39a)

## 13.4 个人信息组件开发

### 13.4.1页面结构和样式渲染如下：

```
<template>
    <view>
	    <view class="avatar-box">
		    <img src="" alt="" class="avatar-img">
		    <text>张三</text>
	    </view>
    </view>
</template>

<style lang="scss">
.avatar-box{
	width:100%;
	height:300rpx;
	background-color: #E43D33;
	position: relative;
	overflow: hidden;
	display: flex;
	flex-direction: column;
	justify-content: space-around;
	align-items: center;
	padding-bottom:40rpx;
	box-sizing: border-box;
	&::before{
		content:'';
		display:block;
		width:100%;
		height:80rpx;
		background-color: #f5f5f5;
		position:absolute;
		bottom:-40rpx;
		left:0;
		border-radius: 100%;
	}
	.avatar-img{
		width:100rpx;
		height:100rpx;
		border-radius: 50%;
		background-color: yellow;
	}
	.vip-img{
		width:100rpx;
		height:100rpx;
	}
	
}
</style>
```
显示如下：
![1.png](https://note.youdao.com/yws/res/6086/WEBRESOURCE0aec9995aa5a08855d0f2b526074b1ba)

### 13.4.2 渲染动态数据

因为和用户信息相关的数据都在store/user.js中的state中的userInfo对象中，所以我们在my-userInfo组件导入并使用如下：

```
<template>
    <view>
	    <view class="avatar-box">
		    <img :src="userInfo.avatarUrl" alt="" class="avatar-img">
		    <text>{{userInfo.nickName}}</text>
	    </view>
    <view>
</template>

<script>
	import {mapState} from 'vuex'
	export default {
		name:"my-userInfo",
		computed:{
			...mapState('m_user',['userInfo'])
		}
	}
</script>
```
### 13.4.3 底部panel列表部分

此部分主要是考研结构和样式的实现，结构如下：


```
<!-- panel列表部分 -->
		<view class="panel-list">
			<!-- 第一个panel部分 -->
			<view class="panel-one">
				<view class="panel-item">
					<text>0</text>
					<view class="panel-item-con">
						<uni-icons type="gift" size="25" color="#FFB6C1"></uni-icons>
						<text>余额</text>
					</view>
				</view>
				<view class="panel-item">
					<text>1934</text>
					<view class="panel-item-con">
						<uni-icons type="medal" size="25" color="#EE82EE"></uni-icons>
						<text>积分</text>
					</view>
				</view>
				<view class="panel-item">
					<text>9</text>
					<view class="panel-item-con">
						<uni-icons type="vip" size="25" color="#32CD32"></uni-icons>
						<text>优惠券</text>
					</view>
				</view>
				<view class="panel-item">
					<text>0</text>
					<view class="panel-item-con">
						<uni-icons type="heart" size="25" color="#00FFFF"></uni-icons>
						<text>礼品卡</text>
					</view>
				</view>
			</view>
			<!-- 第二个panel部分 -->
			<view class="panel-two">
				<view class="panel-title">
					我的订单
				</view>
				<view class="panel-body">
					<view class="panel-item">
						<img src="https://img12.360buyimg.com/img/s60x60_jfs/t1/125209/17/7530/933/5f16524bE43b4a5f7/71971b102d1fcbc5.png" alt="">
						<text>待付款</text>
					</view>
					<view class="panel-item">
						<img src="https://img12.360buyimg.com/img/s120x120_jfs/t1/123660/33/7797/4674/5f1804aeE308173db/b392f9ce63eb8490.png" alt="">
						<text>待收货</text>
					</view>
					<view class="panel-item">
						<img src="https://img12.360buyimg.com/img/s60x60_jfs/t1/120478/38/7592/2211/5f165256E02190e99/1491d4cb340074bb.png" alt="">
						<text>退款/售后</text>
					</view>
					<view class="panel-item">
						<img src="https://img12.360buyimg.com/img/s60x60_jfs/t1/145618/2/3439/692/5f16525eE30cd2db1/3ab434ec2686a256.png" alt="">
						<text>全部订单</text>
					</view>
				</view>
			</view>
			<!-- 第三个panel部分 -->
			<view class="panel-three">
				<view class="panel-item">
					<text>收货地址</text>
					<uni-icons type="right" size="20"></uni-icons>
				</view>
				<view class="panel-item">
					<text>联系客服</text>
					<uni-icons type="right" size="20"></uni-icons>
				</view>
				<view class="panel-item">
					<text>退出登录</text>
					<uni-icons type="right" size="20"></uni-icons>
				</view>
			</view>
		</view>
```

样式如下：

```
// 面板部分
.panel-list{
	width:100%;
	padding: 0 15rpx;
	box-sizing: border-box;
	.panel-one{
		width:100%;
		height:140rpx;
		background-color: #fff;
		border-radius: 10rpx;
		box-shadow: 0 0 3px #C0C4CC;
		display:flex;
		justify-content: space-around;
		align-items:center;
		.panel-item{
			display: flex;
			flex-direction: column;
			justify-content: space-around;
			align-items: center;
			.panel-item-con{
				font-size:24rpx;
				color:#E43D33;
			}
			
		}
		
	}
	.panel-two{
		width:100%;
		height:200rpx;
		border-radius: 10rpx;
		box-shadow: 0 0 3px #C0C4CC;
		margin-top:20rpx;
		background-color: #fff;
		.panel-title{
			height:60rpx;
			font-size:24rpx;
			line-height:60rpx;
			padding-left:10rpx;
			color:#262626;
		}
		.panel-body{
			height:140rpx;
			display: flex;
			justify-content: space-around;
			align-items: center;
			.panel-item{
				width:25%;
				display: flex;
				flex-direction: column;
				justify-content: space-around;
				align-items: center;
				font-size:24rpx;
				img{
					width:60rpx;
					height:60rpx;
				}
			}
		}
	}
	.panel-three{
		width:100%;
		height:300rpx;
		border-radius: 10rpx;
		box-shadow: 0 0 3px #C0C4CC;
		margin-top:20rpx;
		background-color: #fff;
		display: flex;
		flex-direction: column;
		justify-content: space-around;
		.panel-item{
			width:100%;
			height:80rpx;
			line-height: 80rpx;
			display: flex;
			justify-content: space-between;
			align-items: center;
			font-size:28rpx;
			padding:0 10rpx;
			box-sizing: border-box;
		}
	}
	
}
```
显示结果如下：
![1.png](https://note.youdao.com/yws/res/6122/WEBRESOURCE0507df73cc6024f2750efd12ea39abd9)

### 13.4.4 退出登录

- my-userInfo.vue页面添加单击事件

```
<view class="panel-item" @click="logout">
	<text>退出登录</text>
	<uni-icons type="right" size="20"></uni-icons>
</view>
```
- 实现logout事件处理函数

```
import {mapState,mapMutations} from 'vuex'
methods:{
	...mapMutations('m_user',['updateAddress','updateUserInfo','updateToken']),
	logout(){
		this.updateAddress({});
		this.updateUserInfo({})
		this.updateToken('')
	}
}
```
此时点击登录按钮storage中可以看到保存的登录成功的信息，点击退出登录以后可以清除登录的信息内容。

### 13.4.5 跳转到登录页面

就是我们在结算页面，如果我们选择了商品配送地址、商品的数量和价钱，此时如果没有登录会跳转到登录页面，让我们先去登录。
所以我们修改my-settle.vue页面如下：
![7.png](https://note.youdao.com/yws/res/6131/WEBRESOURCE7456d1b538e0a50217380655462b63ff)

### 13.4.6 登录成功之后还调回到原来页面

比如你原来在购物车页面，然后选好商品了，想结算，但是登录之后才能结算，所以跳转到登录页面进行登录，登录成功之后怎么调回到你原来的购物车页面呢？

思路：在跳转之前把跳转的页面信息保存到vuex中方便回来的跳转回去。

具体操作步骤如下:

- store/user.js定义空对象保存登录成功以后的信息内容

```
state:()=>({
		。。。
		// 保存成功以后的用户信息对象
		redirectInfo:null
	})
```


- store/use.js定义更新保存登录成功以后的方法

```
mutations:{
    // 保存登录成功以后的信息对象方法
	updateRedirectInfo(state,info){
		state.redirectInfo=info
	}
}
```
- my-settle.vue页面引入updateRedirectInfo方法并传值（成功以后的success函数来处理）

```
<script>
	import {mapState,mapGetters,mapMutations} from 'vuex'
	export default {
	    。。。
		methods:{
			。。。
			...mapMutations('m_user',['updateRedirectInfo']),
			// 计算总价方法
			countTotal(){
				// 如果商品没有选择不允许点击计算按钮
				if(!this.checkedCount) return uni.showToast({title:'请先选择商品!'})
				// 如果用户没有选择地址,不允许点击计算按钮
				if(!this.addressJoin) return uni.showToast({title:'请选择商品地址!'})
				// 如果用户没有登录,就不能点击计算按钮
				// if(!this.token) return uni.showToast({title:'请先登录'})
				if(!this.token) return uni.switchTab({
					url:'/pages/my/my',
					success:()=>{
						this.updateRedirectInfo({
							'type':'switchTab',
							'from':'/pages/shop/shop'
						})
					}
				})
				
				
			}
		}
	}
</script>
```

- my-login组件引入store/user下面的state数据和更新方法进行判断
![1.png](https://note.youdao.com/yws/res/6088/WEBRESOURCEc2526f0ab1dcaf1c6b462803ebf772af)
![2.png](https://note.youdao.com/yws/res/6125/WEBRESOURCE182bfb1b71f3abce0b5466366094abb5)

此时可以实现上述功能了。

## 13.5 支付功能

### 13.5.1 添加请求token

我们给支付接口添加my字段，所以在项目的main.js中添加过滤，如果有my字段就添加token，否则不能访问。

```
// 请求拦截器
$http.beforeRequest = function (options) {
	// console.log(store,options)  可以打印它看看数据结构和请求携带的参数
  wx.showLoading({
    title: '数据加载中...',
  })
  
  //新添加的地址判断
  if(options.url.indexOf('/my/')!==-1){
	  options.header={
		  Authorization:store.state.m_user.token
	  }
  }
}
```

### 13.5.2 微信支付流程

**思路分析**

-创建订单
前端请求接口把订单商品信息、订单总价、收货地址等发送给服务端，服务端返回前端一个订单编号

-订单预支付
前端请求预支付的接口把订单编号发送给服务器，服务端返回支付的相关参数信息

-发起微信支付
调用uni.requestPayment()这个方法，发起支付


### 13.5.3 创建订单

- my-settle页面添加orderPay方法
![1.png](https://note.youdao.com/yws/res/6089/WEBRESOURCE0e44d759a5f866d08075739b9c4e2f9f)

- orderPay方法具体操作如下：

```
// 订单支付的处理逻辑
			async orderPay(){
			  // 1 获取订单编号
			  // (1)自己拼凑传参对象
			  const orderInfo={
				  // order_price应该是this.checkedTotalPrice 但是调用真正支付接口大家可自己写少点总价 上线的时候再调成this.checkedTotalPrice
				  order_price:0.01,
				  order_address:this.addressJoin,
				  goods:this.cart.filter(item=>item.goods_state).map(x=>({
					  goods_id:x.goods_id,
					  goods_count:x.goods_count,
					  goods_price:x.goods_price

				  }))
			  }
			  // (2)发起请求,获取订单
			  const res=await uni.$http.post('/my/order',orderInfo);
			  const {data,status}=res.data;
			  if(status!==200){
				  return uni.showToast({
				  	title:'获取订单失败',
				  	duration:1000,
				  	icon:'none'
				  })
			  }
			  const ordetNumber=data.orderId;
			  // console.log(ordetNumber)
			  // 2 订单预支付
			}
```
### 13.5.4 订单预支付

订单预支付的接口如下：

```
https://www.fastmock.site/mock/6c3454cb9716e486ccedb6060afe9551/shop/my/prepay
```
所以我们在orderPay方法中拿到订单编号以后我们再调用订单预支付接口获取一些信息，方便我们调用真正微信支付的接口实现传递。

orderPay中添加如下内容：
```
async orderPay(){
			  // 1 获取订单编号
			 。。。
			  const ordetNumber=data.orderId;
			  // 2 订单预支付
			  const prePayRresult=await uni.$http.post('/my/prepay',{'order_number':ordetNumber});
			  const {preInfo:{pay},code}=prePayRresult.data
			  if(code!==200){
			  		return uni.showToast({
			  			title:'获取预支付信息失败',
			  			duration:1000,
			  			icon:'none'
				})
			  }
			  // 3 实现微信支付功能
			}

```
### 13.5.5 实现微信支付功能

我们打开官网查看uniapp中支付接口的具体用法：
![11.png](https://note.youdao.com/yws/res/6105/WEBRESOURCE8b9ca0f21ece27a7240f89aa00a78917)


```
// 3 实现微信支付功能
const result=await uni.requestPayment(pay)
// 我们支付接口没有开通,所以后面的就模拟一下就可以了
// console.log(result)
uni.showToast({
	title:'支付成功',
	duration:1000,
	icon:'none'
})
```

参考链接：

```
https://pay.weixin.qq.com/static/applyment_guide/applyment_detail_miniapp.shtml
```
### 13.5.6 git提交

确保在pay分支上面按步骤执行下面的操作：
1. git add . 
2. git commit -m '完成了支付功能'
3. git push -u origin pay
4. git checkout master
5. git merge pay
6. git push
7. git branch -d pay

# 十四、发布

## 14.1 uniapp发布为小程序
- 打开hubuildx中的发行菜单下面的选项
小程序-微信(使用于uniapp)

- 输入小程序的名称和开发者id,点击发行
![1.png](https://note.youdao.com/yws/res/6081/WEBRESOURCE3b924beb158c134a03aabc456bcd89c9)

- 上面会自动编译，成功后打开微信开发者工具，我们选择上传，添写版本号和项目备注，就会自动上传到微信管理后台。
![1.png](https://note.youdao.com/yws/res/6136/WEBRESOURCE93e15f2fd84e39ca9fe0debc117340d8)

![1.png](https://note.youdao.com/yws/res/6117/WEBRESOURCE5cfc960abcc4bfcc65d2336ae5152af8)

上传成功以后点击确定按钮，然后打开微信开发者平台后台管理查看
![5.png](https://note.youdao.com/yws/res/6109/WEBRESOURCE16bfd4809f0f7573d58b2bc1f6662f36)

- 登录小程序后台--管理--版本管理-提交审核--然后小程序官方通过了以后我们再点击发布就可以正式上线了
![11.png](https://note.youdao.com/yws/res/6156/WEBRESOURCE4aac36e2c1e6f53dc104afe3a39aed67)


## 14.2小程序发布为android版本和ios版本（暂时不能用，得花钱买服务）

- hubilderx登录账号，没有的自己注册一下
点击hubuilderx左下角的未登录，然后进行登录
![1.png](https://note.youdao.com/yws/res/6094/WEBRESOURCE55a806d61732e1b94163fbc7452b6448)

登录账号：webqianduanliu@163.com

- 进行基础配置
![1.png](https://note.youdao.com/yws/res/6144/WEBRESOURCE653c9ea791b3ce7415f7cd7ec0cec22c)

- 进行图标配置（先点击浏览，选择图标，然后生成所有的小图标）
![2.png](https://note.youdao.com/yws/res/6153/WEBRESOURCE1295381b4c927d422b7295caed170b6c)

- 点击hbuilderx中才菜单上面的发行-云打包
![2.png](https://note.youdao.com/yws/res/6162/WEBRESOURCE6a4e99796a34d59c2e6bc0fde6701c25)

- 第一次使用的时候会报下面的信息提示
![3.png](https://note.youdao.com/yws/res/6062/WEBRESOURCE18433c15d7538aadafbb3aeed958fbd7)

- 你登录这个网址把所有信息填完验证了就可以正常打包了

```
https://ask.dcloud.net.cn/account/setting/profile/
```
- 点击打包成功以后会生成一个apk文件，你在自己的安卓手机上安装就能正常使用了。
![11.png](https://note.youdao.com/yws/res/6118/WEBRESOURCEf158fb4714013a61f745fc88e23e3e3c)

