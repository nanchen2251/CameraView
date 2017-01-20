# CameraView  [英文版](https://github.com/nanchen2251/CameraView/blob/master/README.md)
自定义相机，自动聚焦，只是一个自定义View，支持你自主替换UI，支持新老相机。
这不是我自己写的项目，它来源于：[google](https://github.com/google/cameraview)

###我之所以把它放在这里是因为我想让更多的人用起来更加方便，因为原作没有上传到仓库，引用只能下载源码引入。
###但我同时会紧跟官方脚步，及时更新，以让大家用上最合适的相机。

*这是一个预览版本，可能会有所变化*

这不是Google官方的产品

CamaraView的存在是为了让大家使用相机开发更加容易


最低需求API为9. 在9-20仓库使用的是Camera1,而在API20甚至更高的时候是Camera2.


| API Level | Camera API | Preview View |
|:---------:|------------|--------------|
| 9-13      | Camera1    | SurfaceView  |
| 14-20     | Camera1    | TextureView  |
| 21-23     | Camera2    | TextureView  |
| 24        | Camera2    | SurfaceView  |

##你可以这这里看到预览图
![](https://github.com/nanchen2251/CameraView/blob/master/GIF.gif)
## 特性
- 相机预览可以放置在布局Xml,并调用开始的方法可以拍照。
- 你可以配置属性
  - Aspect ratio (app:aspectRatio)
  - Auto-focus (app:autoFocus)
  - Flash (app:flash)

## 使用
现在，它已经被我上传到托管仓库，你可以直接通过下面的步骤使用它
#####Step 1. 在你的主项目中添加
```java
allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
```
#####Step 2. 添加依赖
```java
dependencies {
	        compile 'com.github.nanchen2251:CameraView:1.0.1'
	}
```
#####Step 3.在xml中使用
```xml
<com.google.android.cameraview.CameraView
    android:id="@+id/camera"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:keepScreenOn="true"
    android:adjustViewBounds="true"
    app:autoFocus="true"
    app:aspectRatio="4:3"
    app:facing="back"
    app:flash="auto"/>
```
#####Step 4.在Activity中使用
```java
    @Override
    protected void onResume() {
        super.onResume();
        mCameraView.start();
    }

    @Override
    protected void onPause() {
        mCameraView.stop();
        super.onPause();
    }
```

你也可以看到更多关于如何使用，在demo中。
##关于作者
    南尘<br>
    四川成都<br>
    [博客园](http://www.cnblogs.com/liushilin/)
