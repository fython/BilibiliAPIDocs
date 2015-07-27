## 读取视频排行信息

#### 调用地址

http://api.bilibili.cn/list

需要 App Key

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|tid|true|int|分类编号 new排序为必填 其他为可选|
|exclude_tid|false|int|排除分类编号 不可与tid同时使用|
|mid|false|int|只显示该帐号投稿|
|begin|false|date|起始搜索日期 (格式：YYYY-mm-dd)|
|end|false|date|结束搜索日期 (格式：YYYY-mm-dd)|
|days|false|int|搜索最近天数 范围 1-90天 默认7天|
|page|false|int|结果分页选择 默认为第1页|
|pagesize|false|int|单页返回的记录条数，最大不超过100，默认为30。|
|pinyin|true|string|在使用拼音排序时必填选项 拼音首字母|
|click_detail|false|boolean|可选 返回详细点击信息|
|original|false|boolean|只返回原创投稿|
|mission_id|false|int|返回活动投稿|
|exclude|false|array|排除exclude中的id 可用,分隔多个|
|ver|false|int|API版本 建议使用2|
|order|false|string|排序方式|

##### 排序方式

|字段|说明|
|----|----|
|default|按新投稿排序|
|new|按新评论排序|
|review|按评论数从高至低排序|
|hot|按点击从高至低排序|
|damku|按弹幕数从高至低排序|
|comment|按推荐数从高至低排序|
|promote|按宣传数排序（硬币）|
|pinyin|按标题拼音排序|

#### 返回

|返回值字段|字段类型|字段说明|
|----------|--------|--------|
|code|int|未知|
|name|string|分类名称|
|num|int|返回的记录总数目|
|results|int|返回的记录总数目|
|pages|int|返回的记录总页数|
|list|array|返回数据|

##### 返回字段 "list" 子项

|返回值字段|字段类型|字段说明|
|----------|--------|--------|
|aid|int|视频编号|
|copyright|String|是否原创（Original/Copy）|
|typeid|int|视频分类ID|
|typename|string|视频分类名称|
|title|string|视频标题|
|subtitle|string|视频副标题|
|play|int|播放次数|
|review|int|评论数|
|video_review|int|弹幕数|
|favorites|int|收藏数|
|author|string|视频作者|
|mid|int|视频作者ID|
|create|string|视频创建日期|
|description|string|视频简介|
|pic|string|封面图片地址|
|credit|int|评分数量|
|coins|int|推荐数量|
|duration|string|视频时长|
|comment|int|弹幕数(与video_review一致)|

注意结尾有孤立的 num,类型int，与返回值中的int相同

#### 错误代码

|代码|说明|
|----|----|
|-601|起始日期格式错误|
|-602|结束日期格式错误|
|-603|选择的时间跨度过大|
|-604|沒有输入拼音|
