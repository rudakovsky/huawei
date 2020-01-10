# Manifest
    <uses-permission android:name="com.huawei.permission.external_app_settings.USE_COMPONENT"/>
    <activity android:name="com.huawei.systemmanager.optimize.process.ProtectActivity"></activity>
    
# Call
    Intent intent = new Intent();
    intent.setComponent(new ComponentName("com.huawei.systemmanager", "com.huawei.systemmanager.optimize.process.ProtectActivity"));
    startActivity(intent);
