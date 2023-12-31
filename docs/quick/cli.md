# miniapp_cli指令介绍

框架支持通过miniapp_cli指令快速执行一些能力，miniap_cli为设备上的命令

#### 开启miniapp_cli

需要在cfg.json里打开debugger属性(默认路径为resources/cfg.json)

```javascript
	"debugger": {
		"enable": true
	},
```

#### 截屏

```javascript
//path 为指定设备板子上的截屏路径，保存文件为a.png
miniapp_cli capture {path}/a.png    
```

#### 安装应用

```javascript
//amrPath amr应用在设备板子上所在的路径
miniapp_cli install {amrPath}  
```

#### 卸载应用

```javascript
//appid 应用的appid
miniapp_cli uninstall {appid} 
```

#### 启动应用

```javascript
// appid  应用的appid
miniapp_cli start {appId}  
//跳转到该应用的page页面 在app.json中定义的pageName
miniapp_cli start {appId} {page} 
```

#### monkey测试

需要开启monkey功能才可使用

```javascript
miniapp_cli beginMonkey   //启动monkey
miniapp_cli stopMonkey    //关闭monkey
```

#### 内存打印

```javascript
//打印JS内存
miniapp_cli memoryUsage    
//打印触发GC之后的JS内存
miniapp_cli memoryUsageGC   
//将JS内存输出到/tmp/httpdump.snapshot中
miniapp_cli dumpMemory     
```

#### 启动服务

该功能 需要基于框架V1.4版本，即API Version为 5 才可使用

```javascript
//service 应用的具体服务名
miniapp_cli startService {appId} {service}  
```