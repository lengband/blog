---
title: electron
date: 2021-05-24 22:00:06
tags:
---


npm install --arch=ia32 --platform=win32 electron
> 指定 arch=ia32 来安装32位的electron，在 windows 平台打包都应该基于 32位 来打。
> 这样打出来的包在32位和64位都可以用，维护一套代码就行



坑：
1. 当开启notification的时候，如果设置了交互，需要在macOS对应的通知模块上打开交互的展示

2. Electron使用require报错问题: Uncaught ReferenceError: require is not definend

**解决:**
```javascript
mainWindow = new BrowserWindow({
    width: 800,
    height: 600,
    webPreferences: {
      nodeIntegration: true,
      contextIsolation: false
    }
  });
```