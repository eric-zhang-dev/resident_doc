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

###  根据当前用户查询所申请的评估工单(已经完成的)
- **接口地址：** /ltcins-intact-client-api/client/querySuccessOrderByUserId
- **请求方式：** POST

#### 请求参数
  
参数名称						|描述			|备注
:----						|:---			    |:---
无                           无                   无


####  返回结果

```
{
    "errorCode": 0,
    "errorMsg": null,
    "assessOrderSuccessList": [
        {
            "orderNo": "100201903000001",
            "fullname": "B李四",
            "idcard": "41010020190308005X",
            "sex": "M",
             "relationshipInsUser":1
        },
        {
            "orderNo": "100201903261496",
            "fullname": "曹碧",
            "idcard": "510213196707064746",
            "sex": "F",
             "relationshipInsUser":1
        },
        {
            "orderNo": "100201903281089",
            "fullname": "傅庭波",
            "idcard": "510213197203015013",
            "sex": "M",
             "relationshipInsUser":1
        },
        {
            "orderNo": "100201903282076",
            "fullname": "周维",
            "idcard": "500104198705120834",
            "sex": "M",
             "relationshipInsUser":1
        },
        {
            "orderNo": "100201904031459",
            "fullname": "肖长华",
            "idcard": "510213195303232825",
            "sex": "F",
             "relationshipInsUser":1
        },
        {
            "orderNo": "100201904040964",
            "fullname": "周华芬",
            "idcard": "510213195709192843",
            "sex": "F",
             "relationshipInsUser":1
        },
        {
            "orderNo": "100201905041068",
            "fullname": "丁大淑",
            "idcard": "500104198705120834",
            "sex": "M",
            "relationshipInsUser":1
        }
    ]
}
```

###  根据评估工单号查询具体的护理信息
- **接口地址：** /ltcins-intact-client-api/client/querySuccessOrderInfoByOrderNo
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
    "orderNo": "100201904040964",
    "fullname": "任命",
    "idcard": "510213195709192843",
    "sex": F,
    "relationshipInsUser": 7,
    "assessedLevel": 3,
    "serviceInDate": "2019-04-04",
    "distributeOrgId": 1130,
    "distributeOrgName": "垫江县居家护理专用01",
    "distributeOrgClass": 5,
    "score": 5,
    "planId": "201904041438489284",
    "nursingServicePlanItemInfoList": [
        {
            "frequency": "2日1次",
            "serviceId": 1121,
            "serviceName": "洗发"
        },
        {
            "frequency": "1日1次",
            "serviceId": 1125,
            "serviceName": "精神慰藉"
        }
    ],
    "serviceDuration": 1,
    "serviceCount": 1
}
```
###  根据工单号查询工单详情(居民端app调用)
- **接口地址：** /ltcins-intact-client-api/authed/order_detail.htm
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
  "fullName": "肖长华",	/**参保人姓名*/
  "sex": "2",	/**参保人性别*/
  "birthDay": "",	/**参保人出生年月*/
  "insuredState": 1,	/** 参保状态(1-正常，2-未参保) **/
  "insType": 3,		/** 参保类型(1个人一档 2个人二档 3单位参保) **/
  "newAbode": null,	/**现居地*/
  "detailed": "重庆市重庆市大渡口区湖榕路77号",	/**详细地址*/
  "idCardPics": [],	/**身份证图片地址*/
  "contactName": "覃又香", /**代办人姓名*/
  "contactPhone": "15590908877",	/**代办人联系电话*/
  "contactIdCard": "350128199208258936",	/**代办人身份证号码*/
  "relationshipInsUser": 1,	/**和参保人的关系(0本人 1子女，2父母，3配偶，4（表）兄弟姐妹，5朋友 6其它)**/
  "assessType": 1,	/**申请类型0初评,1复评*/
  "receiveType": 4,	/** 待遇申办类型(1居家上门护理 2机构护理 3居家自主护理（注：现金补助）) **/
  "wantOrgName": "大渡口区护理机构01",	/**申请意向护理机构*/
  "orderStatus": 19,	/** 工单状态*/
  "orderNo": "100201904032203", 	/**工单编号*/
  "createdTime": "2019-04-03 10:42:03", /**申请时间*/
  "pics": [],	/**图片url地址*/
  "payType": null, /**支付方式*/
  "payCost": null,	/**预评估费用*/
  "payTime": null,	/**支付时间*/
  "payNo": null,	/**支付流水号*/
  "appointedTime": "2019-04-04 09:58:48",	/**预约评估时间*/
  "appointedAssessAddress": "湖榕路77号",	/**评估地址*/
  "fullnameA": "评估专家01",	/**评估员a*/
  "fullnameB": "评估员B03", 	/**评估员b*/
  "idcard": "510213195303232825"  /**参保人身份证号码*/
}
```
