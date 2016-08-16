# yunxi-java
云犀直播 JAVA API
云犀直播PHP-SDK, 官方API部分

@author holger whjsjq@gmail.com @link @version 1.0

版本要求

PHP 版本 5.3 及以上

安装

手动引入

require_once('/path/to/Yunxizhibo/Yunxizhibo.php');
接入方法

初始化

$accessKey = 'accessKey';
$secretKey = 'secretKey';
填写AccessKey、SecretKey

$yxObj = new Yunxizhibo($accessKey, $secretKey);
获取活动列表

$data = $yxObj->getActivityList();

if(empty($data)) {
   echo $yxObj->$errCode;
   echo $yxObj->$errMsg;
}
列表

$list = $data["activitys"];
页数

$pageCount = $data["pageCount"];
获取活动资料

 $data = $yxObj->getActivityInfo();

if(empty($data)) {
   echo $yxObj->$errCode;
   echo $yxObj->$errMsg;
}
活动详情

$activity = $data["activity"];
获取直播视频资料

$data = $yxObj->getLivestreamInfo();

if(empty($data)) {
   echo $yxObj->$errCode;
   echo $yxObj->$errMsg;
}
直播视频详情

$livestream = $data["livestream"];
微信嵌入地址

$wechatPlayUrl = $data["wechatPlayUrl"];
网页嵌入地址

$webPlayUrl = $data["webPlayUrl"];
app嵌入地址

$appPlayUrl = $data["appPlayUrl"];
播放器嵌入地址

$embedPlayerUrl = $data["embedPlayerUrl"];
围观人数

$totalNum = $data["totalNum"];
