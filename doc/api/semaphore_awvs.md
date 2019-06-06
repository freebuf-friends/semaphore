---
tags: [semaphore]
keywords: 
last_updated: July 3, 2016
summary: ""
sidebar: semaphore_sidebar
permalink: semaphore_awvs.html
folder: orange
category: API
redirect_from:
    - /doc/api/semaphore_awvs/
title: "Semaphore自动扫描请求"
sort_title: "7"
flag: "2"
---





#### 1)  漏洞扫描请求(REST)

**请求**

URI                 | Method 
------------------- | ---- 
/interface_update/     | Post

**参数** 

名称 | 类型 | 说明
---- | ---- | -------
key | string | 请求密码key。 
domain | string | 需测试服务的域名。 
index | string | 路由。 
file | string | 路由所在源文件名。 
params | string | 路由带参数。 
source | string | 发送扫描请求的服务器IP。 
content | string | 扫描文件的全部源文件文本内容。 



**返回结果** 

```json
{
    "error":"0", //0无错误， -1发生错误
    "errmsg":"none" /* none无错误信息，
                       key is empty!,
                       access key error,
                       source is empty,
                       domain is empty,
                       index is empty,
                       file is empty,
                       params is empty,
                       content is empty */  
}
```



#### 2) 扫描接口(RPC)

**请求**

URI                 | Method 
------------------- | ---- 
/json/     | Post

RPC Method                 | Function 
------------------- | ---- 
sayHello     | What's_the_time 



**参数** 

名称 | 类型 | 说明 
---- | ---- | -------
name | string | 请求扫描的域名。 



**返回结果** 

```json
{
    "Hello ?"  // Hello + 返回域名。
}
```



#### 3) 请求扫描(Command)

**请求**

Command                 | Filename 
------------------- | ---- 
dsl     | dsl.py 



**参数** 

名称 | 类型 | 说明 
---- | ---- | -------
-i —index | string | 路由索引。 
-f —file | string | 文件名。 




**返回结果** 

```json
{
    "Hello ?"  // Hello + 返回域名。
}
```



#### 4) AWVS(库)
##### 4.1）登录

**请求**

Function                 | Filename 
------------------- | ---- 
login     | awvs.py 

**参数** 

无

**返回结果** 

```
{
    True  // True认证成功， False认证失败
}
```



##### 4.2）添加扫描目标

**请求**

Function                 | Filename 
------------------- | ---- 
addTarget     | awvs.py 

**参数** 

名称 | 类型 | 说明 
---- | ---- | -------
domain | string | 域名 

**返回结果** 

```
{
    True  // True扫描域名添加成功， 
          // False扫描域名添加失败
}
```
