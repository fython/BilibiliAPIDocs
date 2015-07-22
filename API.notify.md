## 读取通知信息

#### 调用地址

http://api.bilibili.cn/notify

需要 App Key 并验证登录状态(Access key)

#### 返回

|返回值字段|字段类型|字段说明|
|----------|--------|--------|
|num|int|总通知数目|
|pages|int|返回的记录总页数|
|result|array|返回数据|

##### 返回字段 "result" 子项

|返回值字段|字段类型|字段说明|
|----------|--------|--------|
|nf_id|int|通知ID|
|type|string|通知类型(sys 全体通知 / user 用户通知)|
|title|string|通知标题|
|msg|string|通知內容|
|isread|int|通知读取状态 0为未读取 1为已读|


## 设置通知为已读

#### 调用地址

http://api.bilibili.cn/notify/setread

需要 App Key 并验证登录状态(Access key)

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|nf_id|false|int|通知ID|
|type|false|int|通知类型(sys 全体通知 / user 用户通知)|

#### 错误代码

|代码|说明|
|----|----|
|-1|类型错误|
|-2|通知不存在|
