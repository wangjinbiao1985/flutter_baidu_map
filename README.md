# flutter_baidu_map

百度地图flutter组件。

目前实现直接获取定位功能。


## Getting Started

### 集成百度地图定位android版本

1、先申请一个apikey
http://lbsyun.baidu.com/apiconsole/key

2、修改 `你的项目目录/app/build.gradle`
在`android/defaultConfig`节点修改`manifestPlaceholders`,新增百度地图key配置

```
android {
    .... 你的代码

    defaultConfig {
        .....
         manifestPlaceholders = [
                BAIDU_MAP_KEY : "你的百度地图key", /// 百度地图key
        ]

    }

```


### 集成百度地图定位ios版本

1、申请一个key
http://lbsyun.baidu.com/apiconsole/key

直接在dart文件中设置AK

```
import 'package:flutter_baidu_map/flutter_baidu_map.dart';
   
   void main(){     
       FlutterBaiduMap.setAK("你的AK");
     runApp(new MyApp());
   }
```

2、在info.plist中增加:

```
<key>NSLocationWhenInUseUsageDescription</key>
<string>要用定位</string>
```


在要用的地方导入:

```
import 'package:flutter_baidu_map/flutter_baidu_map.dart';

直接获取定位:

```
await FlutterBaiduMap.getCurrentLocation();
```
