# Android 权限列表

Android 中有上百种权限，现在将所有的权限归为两类：

一类是普通权限
  不会威胁到用户安全和隐私的权限，这部分权限系统会自动帮我们进行授权不需要手动操作

一类的危险权限
 会触及到用户安全隐私或者对设备安全造成影响的权限，必须有用户收到点击授权才可以，否则程序无法使用相应的功能

## 危险权限  9 组 24 个权限
  
- 日历（CALENDAR）
  - READ_CALENDAR
  - WRITE_CALENDAR

- 相机（CAMERA）
  - CAMERA

- 联系人（CONTACTS）
  - READ_CONTACTS
  - WRITE_CONTACTS
  - GET_ACCOUNTS

- 位置（LOCATION）
  - ACCESS_FINE_LOCATION
  - ACCESS_COARSE_LOCATION

- 麦克风（MICROPHONE）
  - RECORD_AUDIO

- 手机（PHONE）
  - READ_PHONE_STATE
  - CALL_PHONE
  - ERAD_CALL_LOG
  - WRITE_CALL_LOG
  - ADD_VOICEMAIL
  - USE_SIP
  - PROCESS_OUTGOING_CALLS

- 传感器（SENSORS）
  - BODY_SENSORS

- 短信（SMS）
  - SEND_SMS
  - RECEIVE_SMS
  - READ_SMS
  - RECEIVE_WAP_PUSH
  - RECEIVE_MMS

- 存储卡（STORAGE）
  - READ_EXTERNAL_STORAGE
  - WRITE_EXTERNAL_STORAGE

---------
不在9组24个权限列表中的权限获取，只需要在 AndroidManifest.xml 文件中添加一下权限声明就可以了

Android O（Android 8.0）系统只会授予应用明确请求的权限。一旦用户为应用授予某个权限，则所有后续对该权限组中权限的请求都将被自动批准。
对于8.0权限，把所用到的危险权限全部申请，如果使用了没有授权的权限，会崩溃的

Android M (6.0)以后，申请权限组一个，即表示整个权限组可以用，所以只要 api 版本大于 23（6.0）,
申请的权限就是申请整个权限组，这样就兼容了Android8.0

```
<uses-permission android:name="andriod.permission.ACCESS_CHECKIN_PROPERTIES" />
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"/>
<uses-permission android:name="android.permission.ACCESS_LOCATION_EXTRA_COMMANDS"/>
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
<uses-permission android:name="android.permission.ACCESS_NOTIFICATION_POLICY"/>
<uses-permission android:name="android.permission.ACCESS_WIFI_STATE"/>
<uses-permission android:name="android.permission.ACCOUNT_MANAGER"/>
<uses-permission android:name="android.permission.ADD_VOICEMAIL"/>
<uses-permission android:name="android.permission.BATTERY_STATS"/>
<uses-permission android:name="android.permission.BIND_ACCESSIBILITY_SERVICE"/>
<uses-permission android:name="android.permission.BIND_CARRIER_MESSAGING_SERVICE"/>
<uses-permission android:name="android.permission.BIND_CARRIER_SERVICES"/>
<uses-permission android:name="android.permission.BIND_CHOOSER_TARGET_SERVICE"/>
<uses-permission android:name="android.permission.BIND_DEVICE_ADMIN"/>
<uses-permission android:name="android.permission.BIND_CONDITION_PROVIDER_SERVICE"/>
<uses-permission android:name="android.permission.BIND_DREAM_SERVICE"/>
<uses-permission android:name="android.permission.BIND_INCALL_SERVICE"/>
<uses-permission android:name="android.permission.BIND_INPUT_METHOD"/>
<uses-permission android:name="android.permission.BIND_MIDI_DEVICE_SERVICE"/>
<uses-permission android:name="android.permission.BIND_NFC_SERVICE"/>
<uses-permission android:name="android.permission.BIND_NOTIFICATION_LISTENER_SERVICE"/>
<uses-permission android:name="android.permission.BIND_PRINT_SERVICE"/>
<uses-permission android:name="android.permission.BIND_QUICK_SETTINGS_TILE"/>
<uses-permission android:name="android.permission.BIND_REMOTEVIEWS"/>
<uses-permission android:name="android.permission.BIND_SCREENING_SERVICE"/>
<uses-permission android:name="android.permission.BIND_TELECOM_CONNECTION_SERVICE"/>
<uses-permission android:name="android.permission.BIND_TEXT_SERVICE" />
<uses-permission android:name="android.permission.BIND_TV_INPUT"/>
<uses-permission android:name="android.permission.BIND_VOICE_INTERACTION"/>
<uses-permission android:name="android.permission.BIND_VPN_SERVICE"/>
<uses-permission android:name="android.permission.BIND_VR_LISTENER_SERVICE"/>
<uses-permission android:name="android.permission.BIND_WALLPAPER"/>
<uses-permission android:name="android.permission.BLUETOOTH"/>
<uses-permission android:name="android.permission.BLUETOOTH_ADMIN"/>
<uses-permission android:name="android.permission.BLUETOOTH_PRIVILEGED"/>
<uses-permission android:name="android.permission.BODY_SENSORS"/>
<uses-permission android:name="android.permission.BROADCAST_PACKAGE_REMOVED"/>
<uses-permission android:name="android.permission.BROADCAST_SMS"/>
<uses-permission android:name="android.permission.BROADCAST_STICKY"/>
<uses-permission android:name="android.permission.BROADCAST_WAP_PUSH"/>
<uses-permission android:name="android.permission.CALL_PHONE"/>
<uses-permission android:name="android.permission.CALL_PRIVILEGED"/>
<uses-permission android:name="android.permission.CAMERA"/>
<uses-permission android:name="android.permission.CAPTURE_AUDIO_OUTPUT"/>
<uses-permission android:name="android.permission.CAPTURE_SECURE_VIDEO_OUTPUT"/>
<uses-permission android:name="android.permission.CAPTURE_VIDEO_OUTPUT"/>
<uses-permission android:name="android.permission.CHANGE_COMPONENT_ENABLED_STATE"/>
<uses-permission android:name="android.permission.CHANGE_CONFIGURATION"/>
<uses-permission android:name="android.permission.CHANGE_NETWORK_STATE"/>
<uses-permission android:name="android.permission.CHANGE_WIFI_MULTICAST_STATE"/>
<uses-permission android:name="android.permission.CHANGE_WIFI_STATE"/>
<uses-permission android:name="android.permission.CLEAR_APP_CACHE"/>
<uses-permission android:name="android.permission.CONTROL_LOCATION_UPDATES"/>
<uses-permission android:name="android.permission.DELETE_CACHE_FILES"/>
<uses-permission android:name="android.permission.DELETE_PACKAGES"/>
<uses-permission android:name="android.permission.DIAGNOSTIC"/>
<uses-permission android:name="android.permission.DISABLE_KEYGUARD"/>
<uses-permission android:name="android.permission.DUMP"/>
<uses-permission android:name="android.permission.EXPAND_STATUS_BAR"/>
<uses-permission android:name="android.permission.FACTORY_TEST"/>
<uses-permission android:name="android.permission.GET_ACCOUNTS"/>
<uses-permission android:name="android.permission.GET_ACCOUNTS_PRIVILEGED"/>
<uses-permission android:name="android.permission.GET_PACKAGE_SIZE"/>
<uses-permission android:name="android.permission.GET_TASKS"/>
<uses-permission android:name="android.permission.GLOBAL_SEARCH"/>
<uses-permission android:name="android.permission.INSTALL_LOCATION_PROVIDER"/>
<uses-permission android:name="android.permission.INSTALL_PACKAGES"/>
<uses-permission android:name="android.permission.INSTALL_SHORTCUT"/>
<uses-permission android:name="android.permission.INTERNET"/>
<uses-permission android:name="android.permission.KILL_BACKGROUND_PROCESSES"/>
<uses-permission android:name="android.permission.LOCATION_HARDWARE"/>
<uses-permission android:name="android.permission.MANAGE_DOCUMENTS"/>
<uses-permission android:name="android.permission.MASTER_CLEAR"/>
<uses-permission android:name="android.permission.MEDIA_CONTENT_CONTROL"/>
<uses-permission android:name="android.permission.MODIFY_AUDIO_SETTINGS"/>
<uses-permission android:name="android.permission.MODIFY_PHONE_STATE"/>
<uses-permission android:name="android.permission.MOUNT_FORMAT_FILESYSTEMS"/>
<uses-permission android:name="android.permission.MOUNT_UNMOUNT_FILESYSTEMS"/>
<uses-permission android:name="android.permission.NFC"/>
<uses-permission android:name="android.permission.PACKAGE_USAGE_STATS"/>
<uses-permission android:name="android.permission.PERSISTENT_ACTIVITY"/>
<uses-permission android:name="android.permission.PROCESS_OUTGOING_CALLS"/>
<uses-permission android:name="android.permission.READ_CALENDAR"/>
<uses-permission android:name="android.permission.READ_CALL_LOG"/>
<uses-permission android:name="android.permission.READ_CONTACTS"/>
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE"/>
<uses-permission android:name="android.permission.READ_FRAME_BUFFER"/>
<uses-permission android:name="android.permission.READ_INPUT_STATE"/>
<uses-permission android:name="android.permission.READ_LOGS"/>
<uses-permission android:name="android.permission.READ_PHONE_STATE"/>
<uses-permission android:name="android.permission.READ_SMS"/>
<uses-permission android:name="android.permission.READ_SYNC_SETTINGS"/>
<uses-permission android:name="android.permission.READ_SYNC_STATS"/>
<uses-permission android:name="android.permission.READ_VOICEMAIL"/>
<uses-permission android:name="android.permission.REBOOT"/>
<uses-permission android:name="android.permission.RECEIVE_BOOT_COMPLETED"/>
<uses-permission android:name="android.permission.RECEIVE_MMS"/>
<uses-permission android:name="android.permission.RECEIVE_SMS"/>
<uses-permission android:name="android.permission.RECEIVE_WAP_PUSH"/>
<uses-permission android:name="android.permission.RECORD_AUDIO"/>
<uses-permission android:name="android.permission.REORDER_TASKS"/>
<uses-permission android:name="android.permission.REQUEST_IGNORE_BATTERY_OPTIMIZATIONS"/>
<uses-permission android:name="android.permission.REQUEST_INSTALL_PACKAGES"/>
<uses-permission android:name="android.permission.RESTART_PACKAGES"/>
<uses-permission android:name="android.permission.SEND_RESPOND_VIA_MESSAGE"/>
<uses-permission android:name="android.permission.SEND_SMS"/>
<uses-permission android:name="android.permission.SET_ALARM"/>
<uses-permission android:name="android.permission.SET_ALWAYS_FINISH"/>
<uses-permission android:name="android.permission.SET_ANIMATION_SCALE"/>
<uses-permission android:name="android.permission.SET_DEBUG_APP"/>
<uses-permission android:name="android.permission.SET_PREFERRED_APPLICATIONS"/>
<uses-permission android:name="android.permission.SET_PROCESS_LIMIT"/>
<uses-permission android:name="android.permission.SET_TIME"/>
<uses-permission android:name="android.permission.SET_TIME_ZONE"/>
<uses-permission android:name="android.permission.SET_WALLPAPER"/>
<uses-permission android:name="android.permission.SET_WALLPAPER_HINTS"/>
<uses-permission android:name="android.permission.SIGNAL_PERSISTENT_PROCESSES"/>
<uses-permission android:name="android.permission.STATUS_BAR"/>
<uses-permission android:name="android.permission.SYSTEM_ALERT_WINDOW"/>
<uses-permission android:name="android.permission.TRANSMIT_IR"/>
<uses-permission android:name="android.permission.UNINSTALL_SHORTCUT"/>
<uses-permission android:name="android.permission.UPDATE_DEVICE_STATS"/>
<uses-permission android:name="android.permission.USE_FINGERPRINT"/>
<uses-permission android:name="android.permission.USE_SIP"/>
<uses-permission android:name="android.permission.VIBRATE"/>
<uses-permission android:name="android.permission.WAKE_LOCK"/>
<uses-permission android:name="android.permission.WRITE_APN_SETTINGS"/>
<uses-permission android:name="android.permission.WRITE_CALENDAR"/>
<uses-permission android:name="android.permission.WRITE_CALL_LOG"/>
<uses-permission android:name="android.permission.WRITE_CONTACTS"/>
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/>
<uses-permission android:name="android.permission.WRITE_GSERVICES"/>
<uses-permission android:name="android.permission.WRITE_SECURE_SETTINGS"/>
<uses-permission android:name="android.permission.WRITE_SETTINGS"/>
<uses-permission android:name="android.permission.WRITE_SYNC_SETTINGS"/>
<uses-permission android:name="android.permission.WRITE_VOICEMAIL"/>
```