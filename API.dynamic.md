## 读取用户动态信息

#### 调用地址

http://api.bilibili.cn/dynamic

需要 App Key 并验证登录状态(Access key)

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|include_types|false|string|选择显示的类型 多个间以半角逗号分隔|
|exclude_types|false|string|忽略特定的类型的动态|
|page|false|int|结果分页选择 默认为第1页|
|pagesize|false|int|单页返回的记录条数，最大不超过100，默认为10。|

##### types 类型常量

|string|说明|
|------|----|
|VIDEO|视频|
|REVIEW|评论|
|NEWS_REVIEW|新闻评论|
|SPECIAL_ADDSP|专题添加专题|
|SPECIAL_ADDBANGUMI|专题添加新番|
|SPECIAL_ADDVIDEO|专题添加视频|
|SPECIAL_BOOK_BANGUMI|连载中的番剧类专题|
|SPECIAL_BOOK_MARK|收藏并关注的专题|
|SPECIAL_BOOK_UNMARK|收藏未关注的专题|
|APP|应用自定义动态|

#### 返回

|返回值字段|字段类型|字段说明|
|----------|--------|--------|
|results|int|返回的记录总数目|
|pages|int|返回的记录总页数|
|list|array|返回数据|


## 添加应用动态

#### 调用地址

http://api.bilibili.cn/dynamic/post

需要 App Key 并验证登录状态(Access key)；应用需要申请应用自定义动态权限

#### 参数


|字段|必选|类型|说明|
|----|----|----|----|
|do|true|string|动态显示的操作（例如：发布了新的投稿）|
|title|true|string|动态显示的标题（例如投稿标题）（不超过60字）|
|link|true|string|动态跳转地址|
|msg|true|string|动态显示的详细信息 （不超过200字）|
|keywords|false|string|站內搜索关键字|
|cover|false|string|显示的封面（不填则显示头像）|

#### 错误代码

|代码|说明|
|----|----|
|-403|应用沒有使用此功能的权限|
