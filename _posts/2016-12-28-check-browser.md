---
layout:post
title:判断浏览器类型
category:Javascript
date:2016-12-27 10:52:19
---
	var Browser=new Object();
	Browser.isMozilla=(typeof document.implementation!='undefined')&&(typeof document.implementation.createDocument!='undefined')&&(typeof HTMLDocument!='undefined');
	Browser.isIE=window.ActiveXObject ? true : false;
	Browser.isFirefox=(navigator.userAgent.toLowerCase().indexOf("firefox")!=-1);
	Browser.isSafari=(navigator.userAgent.toLowerCase().indexOf("safari")!=-1);
	Browser.isOpera=(navigator.userAgent.toLowerCase().indexOf("opera")!=-1);
	Browser.isChrome=(navigator.userAgent.toLowerCase().indexOf('chrome')!=-1);