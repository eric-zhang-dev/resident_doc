# 居民端接口文档

## 1. 接口定义

###  参保人检验
- **接口地址：** /ltcins-intact-client-api/client/loadIns
- **请求方式：** POST

#### 请求参数
  
参数名称						|描述			|备注
:----						|:---			    |:---
idcard						|身份证				|&nbsp;



####  返回结果

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
###  选择护理机构
- **接口地址：** /ltcins-intact-client-api/client/loadWantOrg(中文需编码)
- **请求方式：** POST

#### 请求参数

参数名称						|描述			|备注
:----						|:---			    |:---
receiveType					|待遇申办类型		|5-->居家上门护理，4-->机构护理，6-->居家自主护理，
wantDis						|机构地址				|大渡口区,巴南区,垫江县,石柱土家族自治县


####  返回结果

```
{
	"errorCode": 0,
	"errorMsg": null,
	"dataList": [{
		"orgName": "石柱县居家护理机构",
		"orgId": 1110
	}]
}
```



###  申请评估提交
- **接口地址：** /ltcins-intact-client-api/client/submitOrder
- **请求方式：** POST

#### 请求参数

参数名称						|描述			|备注
:----						|:---			    |:---
fullname					|姓名		    |&nbsp;
idcard						|身份证			  |&nbsp;
sex					        |性别		      |&nbsp;
insType						|参保状态			|1-正常，2-未参保
receiveType					|待遇申办类型		|1职工个人一档 2职工个人二档3单位参保
appointedProvince				|省			|省编码+省
appointedCity					|市		    |市编码+市
appointedDistrict			   |区			|区编码+区
appointedAddress			|详细地址			|

contactName					|代办人姓名		|
contactPhone						|代办人电话			|
contactIdcard					|代办人身份证		|
relationshipInsUser				|与参保人关系			|0本人 1子女，2父母，3配偶，4（表）兄弟姐妹，5朋友 6其它
isReAssess					|申请类型		|
receiveType						|待遇申办类型			|5-->居家上门护理，4-->机构护理，6-->居家自主护理，
wantOrgName					|所属区县		|大渡口区,巴南区,垫江县,石柱土家族自治县
wantOrg						|机构地址			|护理机构编码


####  返回结果

```
{
	"errorCode": 0,
	"errorMsg": null,
}
```
