### 云犀直播JAVA-SDK, 官方API部分
@author  holger <whjsjq@gmail.com>
@link
@version 1.0

## 初始化
```java
   YunxiApi.register(AccessKey, SecretKey);
```

##获取活动列表
```java
   YunxiApi.getActivityList("页码","每页数据条数","unix时间戳");
```  

## 获取活动资料
```java
   YunxiApi.getActivityInfo("活动id","unix时间戳");
```  

## 获取直播视频资料
```java
   YunxiApi.getActivityLiveStream("活动id","unix时间戳"); 
```  
 
