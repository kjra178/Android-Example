AdGem Android SDK
========

Java native mobile optimized AdGem Android SDK.

This is an extenden version of simplified integration guide [here][1].


Download
--------

Download [the latest AAR][2] or grab via Maven:
```xml
<dependency>
  <groupId>com.adgem</groupId>
  <artifactId>adgem-android</artifactId>
  <version>0.6.8</version>
  <type>pom</type>
</dependency>
```
or Gradle:
```groovy
implementation 'com.adgem:adgem-android:0.6.8'
```

AdGem Android SDK requires at minimum Android 4.4.

Overview
--------
AdGem android SDK is automatically configured by a buld system. To configure SDK specifically for your project:
1. Add ```adgem_config.xml``` to ```res/values``` folder of your project structure:
```xml
<adgem-configuration applicationId="1"
                     offerWallEnabled="true"
                     rewardedVideoAdsEnabled="true"
                     standardVideoAdsEnabled="true" />
```
2. Add following tag to ```<application>``` of your ```AndroidManifest.xml```:
```xml
<meta-data android:name="com.adgem.Config"
           android:resource="@xml/adgem_config"/>
```

ProGuard
--------

Proguard config is automatically supplied with AAR. There is no additional configurations needed.

API overview
--------
All communication with SDK can happen via the ```java AdGem``` class:
```java
AdGem adgem = AdGem.get();
```
There is no need to store instance of AdGem globally. SDK will cache it instance on a first call and will always return the same one for all subsequent calls to ```AdGem.get();```

### AdGemCallback:
AdGem SDK offers callbacks that notify when its internal state changes.
```java
AdGem adgem = AdGem.get();
adgem.registerCallback(callback);
```
Once registered, a callback will be used to deliver SDK state change update.

Keep in mind that AdGem will 
### Playing standard videos





[1]: https://help.adgem.com/sdk-integration/android-integration-guide
[2]: https://bintray.com/adgemsdk/android/download_file?file_path=com%2Fadgem%2Fadgem-android%2F0.6.8%2Fadgem-android-0.6.8.aar
