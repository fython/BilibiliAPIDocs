## 读取用户登陆信息

#### 调用地址

https://secure.bilibili.tv/login

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|api|true|string|申请时填入的API地址|
|appkey|true|string|申请时系统提供的Key|
|sign|true|string|校验密钥 md5("api=<API><API_SECRET>")|

#### 回调

编码为UTF-8

|返回值字段|字段类型|字段说明|
|----------|--------|--------|
|mid|int|会员编号|
|uname|string|UTF-8编码 用户暱称|
|face|string|用户头像|
|rank|int|用户等级编码|
|access_key|string|用户访问授权密钥|
|sign|string|校验码 计算方法 见API说明页|

##### 示例

PHP 版本：
```
<?php
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
  $_data[] = $k . '=' . rawurlencode($v);
  }
  $_sign = implode('&', $_data);
  return array(
    'sign' => strtolower(md5($_sign . $key)),
    'params' => $_sign,
  );
 }
 define("APP_SECRET","abcdef123456");
 $params = $_GET;
 unset($params['sign']);
 $sign = get_sign($params,APP_SECRET);
 if ($sign['sign'] != $_GET['sign']) exit("Access denied");
 session_start();
 $_SESSION["access_key"] = $_GET['access_key'];
 header("Location: /favourite.php");
 ?> 
```
