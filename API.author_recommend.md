## 读取作者推荐视频

#### 调用地址

http://api.bilibili.cn/author_recommend

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|aid|true|int|视频ID|

#### 返回

|返回值字段|字段类型|字段说明|
|----------|--------|--------|
|list|array|返回数据|
|code|int|状态代码|

##### 返回字段 "list" 子项

|返回值字段|字段类型|字段说明|
|----------|--------|--------|
|aid|int|视频编号|
|title|string|视频标题|
|cover|string|封面图片地址|
|click|int|点击|
|review|int|评论|
|favorites|int|收藏|
|video_review|int|弹幕|
