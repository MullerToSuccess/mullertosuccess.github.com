---
layout: post
title: Express的route路由详解
date: 2017-02-16 15:32:24.000000000 +09:00
---

##Express的route路由详解
express封装了多种的http请求方式，主要使用get和post，用app.get和app.post的形式获取请求，回调函数有req,res两个参数，分别代表请求信息和响应信息。

- req.query:处理get请求
- req.body:处理post请求

###next()权限控制转移
在定义了多个路由的时候，使用next()对匹配的url按顺序执行

###express中间件：
middleware，收到请求后和发送响应前的阶段执行的一些函数；
中间件的原型：function(req,res,next)
典型的函数：

		app.use('/abcd', function (req, res, next) {
  			console.log(req.baseUrl);
 	 		next();
		})
###express中的session：
	会话；
	保持状态，保持会话；
	http协议是一种无状态协议；
	为了使web应用动起来，客户端出现了脚本和DOM技术，服务器端
	出现了cgi技术；
	一个难题：http无状态协议如何关联两次连续的请求
	两种方案：cookie和session，记录状态：
	cookie保存在客户端即浏览器，session保存在服务器端
	http1.1长连接
	cookie:每个客户端最多保持300个cookie，每个域名下最多20个cookie,每个cookie的大小最多4K，所以要控制cookie的大小
	session:
	基本原理：服务器端为每一个session创建一份会话信息数据，客户端和服务器端依靠一个全局唯一的标识来访问会话信息数据
	创建seesion的三个步骤：
	1. 生成全局唯一标识符sessionid
	2. 开辟数据存储空间
	3. 将全局唯一标识符发给客户端*关键
	数据放到http的请求行，头域或者body中，两种方式：
	cookie和url重写：
	1. cookie：服务器端设置set-cookie头
	2. url重写: get参数的方式加上session标识符
	应用场景：
	1. cookie：remember me服务
	2. session：购物车
	安全性：
	cookie放在客户端，安全性差，需要加密
	session存储在服务器端，相对安全
	性能：
	cookie消耗客户端的i/o和内存，session对服务器的压力大
	