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
insStatus						|参保状态			|1-正常，2-未参保
insType					|待遇申办类型		|1职工个人一档 2职工个人二档3单位参保
appointedProvince				|省			|省编码+省
appointedCity					|市		    |市编码+市
appointedDistrict			   |区			|区编码+区
appointedAddress			|详细地址			|&nbsp;
contactName					|代办人姓名		|&nbsp;
contactPhone						|代办人电话			|&nbsp;
contactIdcard					|代办人身份证		|&nbsp;
relationshipInsUser				|与参保人关系			|0本人 1子女，2父母，3配偶，4（表）兄弟姐妹，5朋友 6其它
isReAssess					|申请类型		|&nbsp;
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
###  我的评估列表
- **接口地址：** /ltcins-intact-client-api/order_query/getList
- **请求方式：** POST

#### 请求参数

参数名称						|描述			|备注
:----						|:---			    |:---
tag					        |状态		        |12-->待受理，3-->待评估，1-->已完成，13-->未通过，14-->已取消
idcard						|身份证				|&nbsp;

####  返回结果

```
{
	"errorCode": 0,
	"errorMsg": null,
	"totalCount": null,
	"totalPage": null,
	"pageNo": null,
	"dataSize": 1,
	"dataList": [{
		"id": null,
		"orderStr": null,
		"orgLinks": "0-1-1103-1160-",
		"orderNo": "100201903261059",
		"orderStatus": 12,
		"protocolId": 1021,
		"applyFrom": 2,
		"paperRecordStatus": 0,
		"applyExpertStatus": 0,
		"applyReAssess": 0,
		"reAssessOrderNo": null,
		"isReAssess": 0,
		"isFollowAssess": 0,
		"isCompleted": 0,
		"completedTime": null,
		"verifiedStauts": 100,
		"verifiedComment": null,
		"verifiedAt": null,
		"verifiedUserId": null,
		"verifiedUserName": null,
		"appleyUserId": null,
		"appleyUserName": "刘盛强",
		"applyRemark": null,
		"applyLongitude": null,
		"applyLatitude": null,
		"applyUserIp": null,
		"appointedTime": null,
		"durationMinute": null,
		"contactName": "您你",
		"contactSex": null,
		"contactIdcard": "快扔咯怕咯了",
		"contactPhone": "低价",
		"appointedRegionId": null,
		"appointedProvince": "348-重庆市",
		"appointedCity": "627-重庆市",
		"appointedDistrict": "2955-大渡口区",
		"appointedAddress": "哦破哦去",
		"appointedLongitude": null,
		"appointedLatidude": null,
		"familyDoctorName": null,
		"familyDoctorPhone": null,
		"familyDoctorCompany": null,
		"appointedAssessRegionId": null,
		"appointedAssessProvince": null,
		"appointedAssessCity": null,
		"appointedAssessDistrict": null,
		"appointedAssessAddress": null,
		"assessOrgId": null,
		"assessOrgName": null,
		"assessUserId": null,
		"assessName": null,
		"appointedAssUserTime": null,
		"lastAssessUserId": null,
		"lastAssessName": null,
		"receiveTime": null,
		"assessSignedBegin": null,
		"assessSignedEnd": null,
		"attendanceType": null,
		"attendanceStatus": null,
		"createdUserId": null,
		"createdUserName": null,
		"createdTime": null,
		"assessedLevel": null,
		"assessCompletedTime": null,
		"updatedTime": null,
		"receiveCutOffTime": null,
		"orderCost": null,
		"orderCostFromGov": null,
		"orderCostFromMyself": null,
		"orderCostFromOther": null,
		"relationshipInsUser": 6,
		"receiveType": 5,
		"wantOrg": 1110,
		"wantOrgName": null,
		"insDistrict": "2984-石柱土家族自治县",
		"insStatus": 1,
		"insType": 1,
		"street": null,
		"assessedScore": null,
		"complaints": null,
		"isComplaints": null,
		"appleyUserIdNo": "513022197908134475",
		"sex": null,
		"avatar": null,
		"medicalInsuranceId": null,
		"insPhone": null,
		"idcard": "513022197908134475",
		"fullname": "刘盛强",
		"special": null,
		"handicapped": null,
		"fullnameA": null,
		"userIdA": null,
		"userIdB": null,
		"workPhoneA": null,
		"fullnameB": null,
		"workPhoneB": null,
		"assessNameLike": null,
		"addressLike": null,
		"longitudeIn": null,
		"latitudeIn": null,
		"attendanceTimeIn": null,
		"attendanceStatusIn": null,
		"medicalHandleOrgRep": null,
		"disAssessOrgRep": null,
		"reviewOpinion": null,
		"reviewOpinionTime": null,
		"reviewOpinionName": null,
		"longitudeOut": null,
		"latitudeOut": null,
		"attendanceTimeOut": null,
		"attendanceStatusOut": null,
		"paperPics": [],
		"startDateAttendance": null,
		"endDateAttendance": null,
		"orderStatusAttendance": null,
		"attendanceStatusQuery": null,
		"terminationOrderReason": null,
		"suspendOrderReason": null,
		"affiliationCompany": "石柱土家族自治县保险公司1",
		"complainant": null,
		"complainantTel": null,
		"complainantContent": null,
		"nurseInsRelation": null
	}]
}

```
###  我的评估列表详情
- **接口地址：** /ltcins-intact-client-api/order_query/getDetail
- **请求方式：** POST

#### 请求参数

参数名称						|描述			|备注
:----						|:---			    |:---
orderNo					    |订单号		        |&nbsp;

####  返回结果

```
{
	"errorCode": 0,
	"errorMsg": null,
	"totalCount": null,
	"totalPage": null,
	"pageNo": null,
	"dataSize": 1,
	"dataList": [{
		"id": null,
		"orderStr": null,
		"orgLinks": null,
		"baseinfokey": 1000000029,
		"certificateType": "1",
		"certificateNumber": "513022197908134475",
		"name": "刘盛强",
		"gender": "2",
		"nation": null,
		"birthday": null,
		"residenceLocation": null,
		"contactName": null,
		"contactPhone": null,
		"nowLocation": null,
		"postalcode": null,
		"personType": null,
		"companyCode": null,
		"bankname": null,
		"bankinfo": null,
		"bankNumber": null,
		"countryCode": "5002400300",
		"datasource": null,
		"updateTime": null,
		"jbNumber": "1018029694",
		"insStatus": "1",
		"insType": "1",
		"insuredDate": "201903",
		"affiliationCompany": null
	}]
}
```