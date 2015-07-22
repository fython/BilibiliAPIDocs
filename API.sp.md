## 读取专题信息

#### 调用地址

http://api.bilibili.cn/sp

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|spid|false|int|专题编号|
|title|false|string|专题名称|

#### 返回

|返回值字段|字段类型|字段说明|
|----------|--------|--------|
|spid|int|专题SPID|
|title|string|专题名|
|pubdate|int|发布日期 (UNIX Timestamp)|
|create_at|date|发布日期|
|lastupdate|int|最后更新日期 (UNIX Timestamp)|
|lastupdate_at|date|最后更新日期|
|alias|string|同义词|
|cover|string|封面|
|isbangumi|int|是否为新番 1=2次元新番 2=3次元新番|
|isbangumi_end|int|是否已经播放结束|
|bangumi_date|date|开播日期|
|description|string|专题简介|
|view|int|点击次数|
|favourite|int|专题收藏次数|
|attention|int|专题被关注次数|
|count|int|专题视频数量|


## 读取用户专题收藏信息

#### 调用地址

http://api.bilibili.cn/sp/list

需要 App Key 并验证登录状态(Access key)

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|page|false|int|结果分页选择 默认为第1页|
|pagesize|false|int|单页返回的记录条数，最大不超过300，默认为10。|
|attention|false|int|关注状态 不传递则返回所有 0：未关注专题 1：已关注专题|

#### 返回

|返回值字段|字段类型|字段说明|
|----------|--------|--------|
|results|int|返回的记录总数目|
|pages|int|返回的记录总页数|
|list|array|返回数据|

##### 返回字段 "list" 子项

|返回值字段|字段类型|字段说明|
|----------|--------|--------|
|spid|int|专题编号|
|title|string|专题标题|
|create_at|string|收藏日期|
|pic|string|封面图片地址|


## 添加专题收藏

#### 调用地址

http://api.bilibili.cn/sp/add

需要 App Key 并验证登录状态(Access key)

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|id|true|int|添加的专题编号|

#### 错误代码

|代码|说明|
|----|----|
|-607|超过收藏上限|


## 删除专题收藏

#### 调用地址

http://api.bilibili.cn/sp/del

需要 App Key 并验证登录状态(Access key)

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|id|true|int|删除的专题编号(同时取消关注)|


## 添加专题关注

#### 调用地址

http://api.bilibili.cn/sp/attention

需要 App Key 并验证登录状态(Access key)

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|id|true|int|添加的专题编号(同时将收藏)|


## 删除专题收藏

#### 调用地址

http://api.bilibili.cn/sp/inattention

需要 App Key 并验证登录状态(Access key)

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|id|true|int|取消关注的专题编号|
