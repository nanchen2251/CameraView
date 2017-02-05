# CameraView [中文版](https://github.com/nanchen2251/CameraView/blob/master/README2.md)
CustomizeCameraView,autofocus,support customize the ui.

This is not my work.just from team [google](https://github.com/google/cameraview)

###The reason why I was in the warehouse was because I wanted to make it easier for everyone to use it

###At the same time I will follow up the development of their team,in order to bring you something better
*This is a preview release. The API is subject to change.*

This is not an official Google product.

CameraView aims to help Android developers easily integrate Camera features.

Requires API Level 9. The library uses Camera 1 API on API Level 9-20 and Camera2 on 21 and above.

| API Level | Camera API | Preview View |
|:---------:|------------|--------------|
| 9-13      | Camera1    | SurfaceView  |
| 14-20     | Camera1    | TextureView  |
| 21-23     | Camera2    | TextureView  |
| 24        | Camera2    | SurfaceView  |

##You can find the preview gif
![](https://github.com/nanchen2251/CameraView/blob/master/GIF.gif)
## Features

- Camera preview by placing it in a layout XML (and calling the start method)
- Configuration by attributes
  - Aspect ratio (app:aspectRatio)
  - Auto-focus (app:autoFocus)
  - Flash (app:flash)

## Usage
Now,it has been synchronized to jitpack by myself.
#####Step 1. Add it in your root build.gradle at the end of repositories:
```java
allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
```
#####Step 2. Add the dependency
```java
dependencies {
	        compile 'com.github.nanchen2251:CameraView:1.0.1'
	}
```
#####Step 3.You can use it to xml
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
#####Step 4.And use it to activity.
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

You can see a complete usage in the demo app.

##my info
    nanchen<br>
    ChengDu SiChuan<br>
    [blogs](http://www.cnblogs.com/liushilin/)
