# 关闭应用安全边界 
*仅测试在Unity上开发Meta Quest应用的情况*

*Last Available in 7.13.2024*

通过在manifest中添加flag的方式实现：
1. 在Unity中导入Meta XR SDK
2. 在Assets/Plugins/Android/Android Manifest.xml中添加以下内容至Application
```
<uses-feature android:name="com.oculus.feature.CONTEXTUAL_BOUNDARYLESS_APP" android:required=true>
```
~*注意，仅对当前应用有效。同时该方法会导致应用无法上架Meta商店，因目前该功能只对少数应用开放，上传任何包括此flag的非白名单应用都会被系统直接拒绝。*~

仅在一体机运行时有效，在串流模式下无效。

该方法已记录于官方开发文档：[Boundaryless](https://developer.oculus.com/documentation/unity/unity-boundaryless/)
