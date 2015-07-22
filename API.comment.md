## 发布弹幕

#### 调用地址

http://api.bilibili.cn/comment/post

需要 App Key 并验证登录状态(Access key)；要求应用申请弹幕权限

#### 参数

|字段|必选|传递方式|类型|说明|
|----|----|--------|----|----|
|mid|true|POST|int|发布帐号(必须和 access_key 帐号一致)|
|cid|true|POST|int|视频ID|
|playTime|true|POST|float|弹幕时间|
|color|true|POST|int|弹幕颜色|
|msg|true|POST|string|发布的信息|
|fontsize|true|POST|int|文字大小|
|mode|true|POST|int|弹幕的模式 (1、普通；4、底端；5、顶端；6、逆向；7、特殊；9、高级)|
|pool|false|POST|int|发布的弹幕池(0、普通；1、字幕；2、特殊)|

#### 错误代码

|代码|说明|
|----|----|
|-634|发送的数据为空|
|-635|该视频不允许发布评论|
|-636|发送的数据不合法|
|-637|系统禁止的信息|
|-638|发布者禁止的信息|
|-639|沒有权限使用该弹幕模式|
|-640|不允许适应期用户发送的信息|
