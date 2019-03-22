# 居民端接口文档

## 1. 接口定义

### 1.1 我的评估
- **接口说明：** 参保人检验
- **接口地址：** /ltcins-intact-client-api/client/loadIns
- **请求方式：** POST

#### 1.1.1 请求参数
  
参数名称						|描述			|备注
:----						|:---			    |:---
idcard						|身份证				|&nbsp;



#### 1.1.2 返回结果

示例：

```
{
	"errorCode": 0,
	"errorMsg": null,
	"baseinfokey": 1000000026,
	"orderNo": null,
	"certificateType": "1",   证件类型
	"certificateNumber": "510213196411204711", 证件号
	"name": "罗忠林",                姓名
	"gender": "2",                     性别1男2女
	"nation": null,                     民族
	"birthday": null,
	"residenceLocation": null,  户口所在地
	"contactName": null,         联系人姓名
	"contactPhone": null,          联系人电话
	"nowLocation": null,          现居地
	"postalcode": null,
	"personType": null,
	"companyCode": null,
	"bankname": null,
	"bankinfo": null,
	"bankNumber": null,
	"countryCode": "5002400300",
	"datasource": null,
	"updateTime": null,
	"jbNumber": "1018027825",
	"insStatus": "1",   参保状态 1 正常 2 未参保
	"insType": "1",      参保类型 1职工个人一档 2职工个人二档3单位参保
	"insuredDate": "201903",
	"affiliationCompany": "石柱土家族自治县保险公司1", 归属保险公司
	"applyType": 0  申请类型
}
```



### 2.2 获取登录用户信息
- **接口说明：** 获取登录用户信息
- **接口地址：** /account/profile

#### 2.1.1 请求参数
  
参数名称						|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
Header						|&nbsp;		|R			|请求报文头
&emsp;Token					|string		|R			|用户登录后token，没有登录则为空字符串
&emsp;Version				|string		|R			|接口版本号
&emsp;SystemId				|int		|R			|机构号，请求的系统Id
&emsp;Timestamp				|long		|R			|当前UNIX时间戳
Body						|&nbsp;		|R			|&nbsp;



请求示例：

```

{
    "Header":{
        "Token":"CA64A439E7C344B0BA7F5C825E17C7AB",
        "Version":"3.2.0",
        "SystemId":100,
        "Timestamp":1502870664
    },
    "Body":null
}

```


#### 2.1.2 返回结果

参数名称						|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
Code						|int		|R			|响应码，代码定义请见“附录A 响应吗说明”
Msg							|string		|R			|&nbsp;
Data						|object		|R			|&nbsp;
&emsp;UserId				|string		|R			|用户Id
&emsp;RealName				|string		|R			|姓名
&emsp;ImageUrl				|string		|R			|头像
&emsp;Score					|int		|R			|积分
&emsp;Nickname				|string		|R			|昵称
&emsp;Sex					|int		|R			|性别：0-未知、1-男、2-女
&emsp;Title					|string		|R			|头衔


示例：

```
{
    "Code":200,
    "Msg":"处理成功",
    "Data":{
        "UserId":"7D916C7283434955A235C17DD9B71C64",
        "RealName":"张三",
        "ImageUrl":"https://img.xx.net/afdicew8751.png",
        "Score":4732,
        "Nickname":"张冠李戴",
        "Sex":1,
        "Title":"侠客Lv4"
    }
}
```