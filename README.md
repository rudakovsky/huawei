# Manifest
    <uses-permission android:name="com.huawei.permission.external_app_settings.USE_COMPONENT"/>
    <activity android:name="com.huawei.systemmanager.optimize.process.ProtectActivity"></activity>
# Check
    mPackageManager = mContext.getPackageManager();
    for (ApplicationInfo appInfo : mPackageManager.getInstalledApplications(PackageManager.GET_META_DATA)) {
       if (appInfo.packageName.equals("com.huawei.systemmanager")) {
         huawei = true;
       }
    }
    
# Call
    Intent intent = new Intent();
    intent.setComponent(new ComponentName("com.huawei.systemmanager", "com.huawei.systemmanager.optimize.process.ProtectActivity"));
    startActivity(intent);
