# Bilibili API 第三方文档
绝大部分内容根据 http://docs.bilibili.cn/wiki 官方文档进行编写
> 哔哩哔哩开放平台为第三方提供了简便的合作模式，满足了网站、手机和平板电脑用户随时随地观看哔哩哔哩的需求。哔哩哔哩开放平台提供相关接口，以实现第三方WAP站和客户端等多种应用的接入。

### API 分类

[作者推荐](./API.author_recommend.md)；
[番剧](./API.bangumi.md)；
[弹幕](./API.comment.md)；
[动态](./API.dynamic.md)；

[视频/专题收藏、关注](./API.favourite.md)；
[视频评论](./API.feedback.md)；
[好友/悄悄关注/黑名单](./API.friend.md)；

[历史记录](./API.history.md)；
[批量获取排行信息(首页)](./API.index.md)；
[获取视频排行信息](./API.list.md)；

[登录行为记录](./API.log.md)；
[第三方登录](./API.login.3rd.md)；
[登录](./API.login.md)；

[我的信息](./API.myinfo.md)；
[通知](./API.notify.md)；
[视频推荐](./API.recommend.md)；
[搜索](./API.search.md)；
[读取/创建专题](./API.sp.md)；

[番剧专题](./API.spview.md)；
[搜索关键词](./API.suggest.md)；
[标签](./API.tags.md)；
[用户信息](./API.userinfo.md)；
[获取视频信息](./API.view.md)。


### 注意事项

##### 关于滥用
以下这些，但并不限于以下这些行为都被视为滥用：
a.短时间内大量操作API用于采集。
b.测试帐号及密码
c.其它没有提到的，但会给系统带来压力的请求行为。

##### 禁止登录

如果账号尝试登录错误次数在 30 分钟内超过 5 次则会被禁止登录一个小时，写程序的时候特别是 客户端的时候必须判断是否登录成功，如果不成功必须马上停止尝试。

##### 关于封禁

由于滥用 API 将会导致 API 被封禁，但并不影响在官方网站上的使用，封禁一定的时间后会自动解除，一般需要一个小时后才会解封，所以请小心操作，不要拿 API 进行大量测试

##### 请求地址

请求的地址为 http://api.bilibili.com/ 开头的地址

##### 请求方法

只支持 GET 方法请求数据，用其它方法会提示相关错误。

##### 关于编码

请用 UTF-8 编码进行数据传输，返回的数据也是 UTF-8 编码的。

##### 关于 UserAgent

请求的时候必须设置 UserAgent，如果不设置或者设置为不合法的（比如设置为浏览器的）也会导致账号被封禁 API。 UserAgent 的格式必须为：程序英文名称/版本 (联系邮箱) 比如：BiLiBiLi WP Client/1.0.0 (orz@loli.my)


### 通用调用参数

|字段|必选|类型|说明|
|----|----|----|----|
|type|false|string (json/xml/jsonp)|返回数据方式 默认json|
|appkey|true|string|应用appkey|
|ts|true|int|当前时间截 (UNIX TIMESTAMP)|
|sign|true|string|应用校验密匙|
|callback|false|string|JSONp调用方式时回调函数名称|
|access_key|false|string|应用在用户申请登陆后获取到的access_key 可以此access_key访问需要用户权限的操作|
|platform|false|string (android/ios)|客户端平台适配及统计用|

### 通用错误代码

|代码|说明|
|----|----|
|-1|应用程序不存在或已被封禁|
|-2|Access key错误|
|-3|API校验密匙错误|
|-101|帐号未登陆|
|-102|帐号被封停|
|-103|积分不足|
|-104|硬币不足|
|-105|验证码错误|
|-106|帐号未激活|
|-107|帐号非正式会员或在适应期|
|-108|应用沒有存取相应功能的权限|
|-400|请求有误|
|-403|权限不足|
|-404|文档不存在|
|-500|服务器内部错误|
|-503|调用速度过快|

### 签名(sign)生成方式

把接口所需所有参数拼接，如utk=xx&time=xx，按参数名称排序，最后再拼接上密钥App-Secret，做md5加密 (callback不需要参与sign校检)

##### 代码示例

PHP 版本:

```
/**
 * @param $params array 参数列表
 * @param $key 加密密钥
 * @return array sign:加密校验串,params:参数拼接串
 */
 function get_sign($params, $key) {
  $_data = array();
  ksort($params);
  reset($params);
  foreach ($params as $k => $v) {
  // rawurlencode 返回的转义数字必须为大写( 如%2F )
  $_data[] = $k . '=' . rawurlencode($v);
  }
  $_sign = implode('&', $_data);
  return array(
    'sign' => strtolower(md5($_sign . $key)),
    'params' => $_sign,
  );
 }
 define("APP_SECRET","abcdef123456");
 get_sign(array("type"=>"json"),APP_SECRET);
```

JS 版本:

```
<script type="text/javascript" src="http://static.hdslb.com/js/md5.js">/script>
 function get_sign(params, key)
 {
 	var s_keys = [];
 	for (var i in params)
 	{
 		s_keys.push(i);
 	}
 	s_keys.sort();
 	var data = "";
 	for (var i = 0; i < s_keys.length; i++)
 	{
 		// encodeURIComponent 返回的转义数字必须为大写( 如 %2F )
 		data+=(data ? "&" : "")+s_keys[i]+"="+encodeURIComponent(params[s_keys[i]]);
 	}
 	return {
 		"sign":hex_md5(data+key),
 		"params":data
 	};
 }
```
