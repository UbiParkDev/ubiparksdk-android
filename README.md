# ubiparksdk-android
UbiPark SDK for Android

### Requirements
#### AndroidManifest.xml
The permissions and service is the absolute minimum required to allow the SDK to run.
```xml
<uses-permission android:name="android.permission.BLUETOOTH" />
<uses-permission android:name="android.permission.BLUETOOTH_ADMIN" />
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
<uses-permission android:name="android.permission.WAKE_LOCK" />

<application ...>
  ...
  <service android:enabled="true" android:name="com.ubipark.ubiparksdk.services.BeaconSDKService" android:permission="android.permission.BIND_JOB_SERVICE"/>
</application>
```

If you want the SDK to start when the device starts, you may add this to your xml:
```xml
<uses-permission android:name="android.permission.RECEIVE_BOOT_COMPLETED" />

<application ...>
    ...

    <receiver android:name="com.ubipark.ubiparksdk.services.BeaconSDKServiceReceiver" >
        <intent-filter>
            <action android:name="android.intent.action.BOOT_COMPLETED" />
        </intent-filter>
    </receiver>
</application>
```
