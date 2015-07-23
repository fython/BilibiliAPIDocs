## 获取用户信息

#### 调用地址

http://api.bilibili.cn/userinfo

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|user|false|string|要查询的昵称 (mid 或 user必须有其中之一)|
|uid|false|int|要查询的帐号id (mid 或 user必须有其中之一)|

#### 返回（坑爹的时刻来了！）

通过昵称获取和通过 uid 获取的数据格式是不一样的！！！！
尼玛而且昵称获取到的信息比 uid 还要多！！！！

##### 通过 user 获取的返回值

|返回值字段|字段类型|字段说明|
|----------|--------|--------|
|mid|int|会员ID|
|name|string|暱名|
|approve|int|是否为认证帐号|
|sex|string|性别 (男/女/不明)|
|rank|int|帐号显示标识|
|face|string|小头像|
|attention|int|关注的好友人数|
|fans|int|粉丝人数|
|article|int|投稿数|
|place|string|所在地|
|description|string|认证用户为认证信息 普通用户为交友宣言|
|attentions|array|关注的好友列表|

##### 通过 uid 获取的返回值

|返回值字段|字段类型|字段说明|
|----------|--------|--------|
|mid|int|会员ID|
|uname|string|暱名|
|userid|string|用户名|
|face|string|头像|
|rank|int|帐号显示标识|
|sex|string|性别 (男/女/不明)|
|sign|string|认证用户为认证信息 普通用户为交友宣言|
