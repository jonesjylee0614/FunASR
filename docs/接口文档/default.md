# api接口文档


**简介**:api接口文档


**HOST**:


**联系人**:


**Version**:1.0


**接口路径**:/v3/api-docs


[TOC]






# 声纹管理


## 删除用户声纹


**接口地址**:`/voice/print/del`


**请求方式**:`DELETE`


**请求数据类型**:`application/x-www-form-urlencoded,application/json`


**响应数据类型**:`application/json`


**接口描述**:


**请求示例**:


```javascript
{
  "docId": "",
  "userId": 0
}
```


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|domain.dto.VoiceUserPrintDelReq|domain.dto.VoiceUserPrintDelReq|body|true|domain.dto.VoiceUserPrintDelReq|domain.dto.VoiceUserPrintDelReq|
|&emsp;&emsp;docId|声纹ID||true|string||
|&emsp;&emsp;userId|用户ID||true|json.JsonInt64||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Base|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|appName|应用名，接口报错时会有此字段，可作为报错参考依据|string||
|code|状态码, 200或0：正常，其他：错误|int|int|
|data|数据|object||
|message|状态描述|string||
|success|是否成功|boolean||
|time|毫秒时间戳|string||
|traceId|日志id，接口报错时会有此字段，可作为报错日志快速定位依据|string||


**响应示例**:
```javascript
{
	"appName": "app",
	"code": 200,
	"data": {},
	"message": "success",
	"success": true,
	"time": 1761039207689,
	"traceId": "efc1cea2"
}
```


## 获取用户列表


**接口地址**:`/voice/print/getUserList`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`application/json`


**接口描述**:<p>该列表的用户需要有[声纹注册用户]角色权限</p>



**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|page|page 默认(1)|query|false|json.JsonInt64||
|pageSize|pageSize 默认(10)|query|false|json.JsonInt64||
|name|用户名|query|false|string||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Base«model.base.PageResult[core.BusinessAccount]»|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|appName|应用名，接口报错时会有此字段，可作为报错参考依据|string||
|code|状态码, 200或0：正常，其他：错误|int|int|
|data|数据|model.base.PageResult[core.BusinessAccount]|model.base.PageResult[core.BusinessAccount]|
|&emsp;&emsp;items|items|array|model.core.BusinessAccount|
|&emsp;&emsp;&emsp;&emsp;address|address|string||
|&emsp;&emsp;&emsp;&emsp;appKey|appKey|string||
|&emsp;&emsp;&emsp;&emsp;appKeySecret|appKeySecret|string||
|&emsp;&emsp;&emsp;&emsp;area|area|string||
|&emsp;&emsp;&emsp;&emsp;avatar|avatar|string||
|&emsp;&emsp;&emsp;&emsp;city|city|string||
|&emsp;&emsp;&emsp;&emsp;company|company|string||
|&emsp;&emsp;&emsp;&emsp;createTime|createTime|pkg.json.JsonTime|pkg.json.JsonTime|
|&emsp;&emsp;&emsp;&emsp;creatorId|creatorId|int64||
|&emsp;&emsp;&emsp;&emsp;creatorName|creatorName|string||
|&emsp;&emsp;&emsp;&emsp;dept_id|dept_id|int64||
|&emsp;&emsp;&emsp;&emsp;email|email|string||
|&emsp;&emsp;&emsp;&emsp;fileSize|fileSize|uint64||
|&emsp;&emsp;&emsp;&emsp;id|id|int64||
|&emsp;&emsp;&emsp;&emsp;lastLoginIp|lastLoginIp|string||
|&emsp;&emsp;&emsp;&emsp;lastLoginTime|lastLoginTime|int64||
|&emsp;&emsp;&emsp;&emsp;loginstatus|loginstatus|bool||
|&emsp;&emsp;&emsp;&emsp;mobile|mobile|string||
|&emsp;&emsp;&emsp;&emsp;name|name|string||
|&emsp;&emsp;&emsp;&emsp;nickname|nickname|string||
|&emsp;&emsp;&emsp;&emsp;password|password|string||
|&emsp;&emsp;&emsp;&emsp;province|province|string||
|&emsp;&emsp;&emsp;&emsp;remark|remark|string||
|&emsp;&emsp;&emsp;&emsp;salt|salt|string||
|&emsp;&emsp;&emsp;&emsp;status|status|int64||
|&emsp;&emsp;&emsp;&emsp;tel|tel|string||
|&emsp;&emsp;&emsp;&emsp;uid|uid|int64||
|&emsp;&emsp;&emsp;&emsp;updateTime|updateTime|pkg.json.JsonTime|pkg.json.JsonTime|
|&emsp;&emsp;&emsp;&emsp;updaterId|updaterId|int64||
|&emsp;&emsp;&emsp;&emsp;updaterName|updaterName|string||
|&emsp;&emsp;&emsp;&emsp;username|username|string||
|&emsp;&emsp;&emsp;&emsp;validtime|validtime|int64||
|&emsp;&emsp;page|page|int64||
|&emsp;&emsp;pageSize|pageSize|int64||
|&emsp;&emsp;total|total|int64||
|message|状态描述|string||
|success|是否成功|boolean||
|time|毫秒时间戳|string||
|traceId|日志id，接口报错时会有此字段，可作为报错日志快速定位依据|string||


**响应示例**:
```javascript
{
	"appName": "app",
	"code": 200,
	"data": {
		"items": [
			{
				"address": "",
				"appKey": "",
				"appKeySecret": "",
				"area": "",
				"avatar": "",
				"city": "",
				"company": "",
				"createTime": {},
				"creatorId": 0,
				"creatorName": "",
				"dept_id": 0,
				"email": "",
				"fileSize": 0,
				"id": 0,
				"lastLoginIp": "",
				"lastLoginTime": 0,
				"loginstatus": false,
				"mobile": "",
				"name": "",
				"nickname": "",
				"password": "",
				"province": "",
				"remark": "",
				"salt": "",
				"status": 0,
				"tel": "",
				"uid": 0,
				"updateTime": {},
				"updaterId": 0,
				"updaterName": "",
				"username": "",
				"validtime": 0
			}
		],
		"page": 0,
		"pageSize": 0,
		"total": 0
	},
	"message": "success",
	"success": true,
	"time": 1761039207689,
	"traceId": "578d91fe"
}
```


## 获取用户声纹列表


**接口地址**:`/voice/print/getUserPrints`


**请求方式**:`GET`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`application/json`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|userId|用户ID|query|true|json.JsonInt64||
|page|page 默认(1)|query|false|json.JsonInt64||
|pageSize|pageSize 默认(10)|query|false|json.JsonInt64||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Base«model.base.PageResult[dto.VoiceUserPrintPageData]»|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|appName|应用名，接口报错时会有此字段，可作为报错参考依据|string||
|code|状态码, 200或0：正常，其他：错误|int|int|
|data|数据|model.base.PageResult[dto.VoiceUserPrintPageData]|model.base.PageResult[dto.VoiceUserPrintPageData]|
|&emsp;&emsp;items|items|array|domain.dto.VoiceUserPrintPageData|
|&emsp;&emsp;&emsp;&emsp;create_time|创建时间|int64||
|&emsp;&emsp;&emsp;&emsp;id|用户ID|string||
|&emsp;&emsp;&emsp;&emsp;txt|文字信息|string||
|&emsp;&emsp;&emsp;&emsp;userid|用户ID|int64||
|&emsp;&emsp;&emsp;&emsp;username|用户姓名|string||
|&emsp;&emsp;&emsp;&emsp;wav_path|音频文件 通过拼接接口域名+userid可访问|string||
|&emsp;&emsp;page|page|int64||
|&emsp;&emsp;pageSize|pageSize|int64||
|&emsp;&emsp;total|total|int64||
|message|状态描述|string||
|success|是否成功|boolean||
|time|毫秒时间戳|string||
|traceId|日志id，接口报错时会有此字段，可作为报错日志快速定位依据|string||


**响应示例**:
```javascript
{
	"appName": "app",
	"code": 200,
	"data": {
		"items": [
			{
				"create_time": 0,
				"id": "",
				"txt": "",
				"userid": 0,
				"username": "",
				"wav_path": ""
			}
		],
		"page": 0,
		"pageSize": 0,
		"total": 0
	},
	"message": "success",
	"success": true,
	"time": 1761039207689,
	"traceId": "c0185169"
}
```


## 声纹鉴定


**接口地址**:`/voice/print/identify`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`application/json`


**接口描述**:<p>上传或录制音频,返回声纹鉴定结果及文字信息</p>



**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|audio|音频文件|query|true|file||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Base«domain.dto.UserPrintIdentifyRes»|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|appName|应用名，接口报错时会有此字段，可作为报错参考依据|string||
|code|状态码, 200或0：正常，其他：错误|int|int|
|data|数据|domain.dto.UserPrintIdentifyRes|domain.dto.UserPrintIdentifyRes|
|&emsp;&emsp;txt|音频中的文本信息|string||
|&emsp;&emsp;user|声纹鉴定出的用户信息|model.core.BusinessAccount|model.core.BusinessAccount|
|&emsp;&emsp;&emsp;&emsp;address|address|string||
|&emsp;&emsp;&emsp;&emsp;appKey|appKey|string||
|&emsp;&emsp;&emsp;&emsp;appKeySecret|appKeySecret|string||
|&emsp;&emsp;&emsp;&emsp;area|area|string||
|&emsp;&emsp;&emsp;&emsp;avatar|avatar|string||
|&emsp;&emsp;&emsp;&emsp;city|city|string||
|&emsp;&emsp;&emsp;&emsp;company|company|string||
|&emsp;&emsp;&emsp;&emsp;createTime|createTime|pkg.json.JsonTime|pkg.json.JsonTime|
|&emsp;&emsp;&emsp;&emsp;creatorId|creatorId|int64||
|&emsp;&emsp;&emsp;&emsp;creatorName|creatorName|string||
|&emsp;&emsp;&emsp;&emsp;dept_id|dept_id|int64||
|&emsp;&emsp;&emsp;&emsp;email|email|string||
|&emsp;&emsp;&emsp;&emsp;fileSize|fileSize|uint64||
|&emsp;&emsp;&emsp;&emsp;id|id|int64||
|&emsp;&emsp;&emsp;&emsp;lastLoginIp|lastLoginIp|string||
|&emsp;&emsp;&emsp;&emsp;lastLoginTime|lastLoginTime|int64||
|&emsp;&emsp;&emsp;&emsp;loginstatus|loginstatus|bool||
|&emsp;&emsp;&emsp;&emsp;mobile|mobile|string||
|&emsp;&emsp;&emsp;&emsp;name|name|string||
|&emsp;&emsp;&emsp;&emsp;nickname|nickname|string||
|&emsp;&emsp;&emsp;&emsp;password|password|string||
|&emsp;&emsp;&emsp;&emsp;province|province|string||
|&emsp;&emsp;&emsp;&emsp;remark|remark|string||
|&emsp;&emsp;&emsp;&emsp;salt|salt|string||
|&emsp;&emsp;&emsp;&emsp;status|status|int64||
|&emsp;&emsp;&emsp;&emsp;tel|tel|string||
|&emsp;&emsp;&emsp;&emsp;uid|uid|int64||
|&emsp;&emsp;&emsp;&emsp;updateTime|updateTime|pkg.json.JsonTime|pkg.json.JsonTime|
|&emsp;&emsp;&emsp;&emsp;updaterId|updaterId|int64||
|&emsp;&emsp;&emsp;&emsp;updaterName|updaterName|string||
|&emsp;&emsp;&emsp;&emsp;username|username|string||
|&emsp;&emsp;&emsp;&emsp;validtime|validtime|int64||
|message|状态描述|string||
|success|是否成功|boolean||
|time|毫秒时间戳|string||
|traceId|日志id，接口报错时会有此字段，可作为报错日志快速定位依据|string||


**响应示例**:
```javascript
{
	"appName": "app",
	"code": 200,
	"data": {
		"txt": "",
		"user": {
			"address": "",
			"appKey": "",
			"appKeySecret": "",
			"area": "",
			"avatar": "",
			"city": "",
			"company": "",
			"createTime": {},
			"creatorId": 0,
			"creatorName": "",
			"dept_id": 0,
			"email": "",
			"fileSize": 0,
			"id": 0,
			"lastLoginIp": "",
			"lastLoginTime": 0,
			"loginstatus": false,
			"mobile": "",
			"name": "",
			"nickname": "",
			"password": "",
			"province": "",
			"remark": "",
			"salt": "",
			"status": 0,
			"tel": "",
			"uid": 0,
			"updateTime": {},
			"updaterId": 0,
			"updaterName": "",
			"username": "",
			"validtime": 0
		}
	},
	"message": "success",
	"success": true,
	"time": 1761039207689,
	"traceId": "926f6fdc"
}
```


## 保存用户声纹信息


**接口地址**:`/voice/print/saveUserPrint`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`application/json`


**接口描述**:


**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|userId|用户id|query|true|int||
|userName|用户姓名|query|true|string||
|audio|音频文件|query|true|file||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Base|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|appName|应用名，接口报错时会有此字段，可作为报错参考依据|string||
|code|状态码, 200或0：正常，其他：错误|int|int|
|data|数据|object||
|message|状态描述|string||
|success|是否成功|boolean||
|time|毫秒时间戳|string||
|traceId|日志id，接口报错时会有此字段，可作为报错日志快速定位依据|string||


**响应示例**:
```javascript
{
	"appName": "app",
	"code": 200,
	"data": {},
	"message": "success",
	"success": true,
	"time": 1761039207689,
	"traceId": "efc1cea2"
}
```


# 离线会议


## 创建离线会议


**接口地址**:`/meeting/offline/save`


**请求方式**:`POST`


**请求数据类型**:`application/x-www-form-urlencoded`


**响应数据类型**:`application/json`


**接口描述**:<p>通过上传离线会议音频，自动识别发言人，拆分发言文字</p>



**请求参数**:


| 参数名称 | 参数说明 | 请求类型    | 是否必须 | 数据类型 | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|name|会议名|query|true|string||
|meetingTime|会议时间 格式 yyyy-MM-dd HH:mm:ss|query|true|string||
|audio|音频文件|query|true|file||


**响应状态**:


| 状态码 | 说明 | schema |
| -------- | -------- | ----- | 
|200|OK|Base|


**响应参数**:


| 参数名称 | 参数说明 | 类型 | schema |
| -------- | -------- | ----- |----- | 
|appName|应用名，接口报错时会有此字段，可作为报错参考依据|string||
|code|状态码, 200或0：正常，其他：错误|int|int|
|data|数据|object||
|message|状态描述|string||
|success|是否成功|boolean||
|time|毫秒时间戳|string||
|traceId|日志id，接口报错时会有此字段，可作为报错日志快速定位依据|string||


**响应示例**:
```javascript
{
	"appName": "app",
	"code": 200,
	"data": {},
	"message": "success",
	"success": true,
	"time": 1761039207689,
	"traceId": "efc1cea2"
}
```