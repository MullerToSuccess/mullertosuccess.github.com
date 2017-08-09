---
layout: post
title: windows下 Nodejs完全删除
date: 2017-05-10 15:32:24.000000000 +09:00
---
#windows下 Nodejs完全删除
	1>程序和功能:卸载nodejs
	2>删除以下目录 C:\Program Files (x86)\Nodejs C:\Program Files\Nodejs C:\Users\{User}\AppData\Roaming\npm (or %appdata%\npm) C:\Users\{User}\AppData\Roaming\npm-cache (or %appdata%\npm-cache)
	3>检查环境变量path中是否存在Nodejs 或者npm
	4>重启