### UEditor 集成腾讯云 COS

基于 [UEditor 1.4.3.3 PHP 版](http://ueditor.baidu.com)和 [腾讯云 COS PHP SDK](https://github.com/tencentyun/cos-php-sdk-v5) 开发。

#### 功能

1. 单图和多图同时上传到腾讯云 COS
2. 附件同时上传到腾讯云 COS
3. 支持 log 记录

#### 使用

1、下载后解压为 `ueditor`（不支持其它的项目名称）

2、安装腾讯云 COS PHP SDK

```
$ composer install
```

3、修改文件 `php/qcloud.config.sample.php` 为 `php/qcloud.config.php`，并配置：

```
<?php
$region = '';   // 地域，比如：上海是 ap-shanghai
$secretId = '';     // 云 API 密钥的一部分，SecretId 用于标识 API 调用者身份。
$secretKey = '';     // 云 API 密钥的一部分，SecretKey 是用于加密签名字符串和服务器端验证签名字符串的密钥。
$bucketname = ''; // 空间名
```

4、修改文件 `php/config.sample.json` 为 `php/config.json`，并配置：

```
/* 上传图片配置项 */
……
"imageUrlPrefix": "", /* 图片访问路径前缀，腾讯云 COS 域名配置，如：http://xxxx.xxxx.xxxx */
……
/* 上传文件配置 */
……
"fileUrlPrefix": "", /* 文件访问路径前缀，腾讯云 COS 域名配置，如：http://xxxx.xxxx.xxxx */
```

说明：上传到腾讯云失败，可以查看 `php/log.txt` 文件里的详细错误信息。

#### 注意

1. 保证 php 目录有写的权限；
2. php 安装有 curl 扩展。
