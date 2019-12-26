# JzCrashHandler
實現一行代碼優雅的處理安卓崩潰問題．
## 目錄
* [如何導入到專案](#Import)
* [快速使用](#Use)
* [關於我](#About)

<a name="Import"></a>
## 如何導入到項目
> 支持jcenter。 <br/>

### jcenter導入方式
在app專案包的build.gradle中添加
```kotlin
allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
```

在需要用到這個庫的module中的build.gradle中的dependencies中加入
```kotlin
dependencies {
implementation 'com.github.sam38124: JzCrashHandler:1.0'
}
```
<a name="Use"></a>
## 快速使用

### 於Application中添加你的崩潰處理方式 
```kotlin
/*MainActivity::class.java為你要重新起動app的進入點*/

//1.崩潰後自動重啟
CrashHandle.newInstance(this,MainActivity::class.java).SetUp(CrashHandle.RESTART)
//2.崩潰後顯示Log紀錄檔
CrashHandle.newInstance(this,MainActivity::class.java).SetUp(CrashHandle.SHOW_CRASH_MESSAGE)
//3.崩潰後上傳Log紀錄檔
CrashHandle.newInstance(this,MainActivity::class.java).SetUp(CrashHandle.UPLOAD_CRASH_MESSAGE)
```
### 其他 
```kotlin
CrashHandle.getInstance().ReadLog()//讀取崩潰紀錄

CrashHandle.getInstance().DeltetRecord()//刪除崩潰紀錄
```
<a name="About"></a>
### 關於我
橙的電子Android and Ios Developer

*line:sam38124

*gmail:sam38124@gmail.com
