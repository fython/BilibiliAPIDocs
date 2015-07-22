## 读取用户信息

#### 调用地址

http://api.bilibili.cn/myinfo

需要 App Key 并验证登录状态(Access key)

#### 返回

|返回值字段|字段类型|字段说明|
|----------|--------|--------|
|mid|int|用户ID|
|uname|string|用户名称|
|face|string|头像图片地址|
|rank|int|用户等级|
|scores|int|积分|
|coins|int|金币|
|attentions|int|关注的用户列表|
|sex|string|性别|
|maxstow|int|最大收藏上限|

##### 用户等级数值解释

|数字|等级名称|
|----|--------|
|0|普通会员|
|5000|注册会员|
|10000|正式会员|
|20000|字幕君|
|25000|VIP|
|30000|真·职人|
