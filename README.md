# Manifest
    <uses-permission android:name="com.huawei.permission.external_app_settings.USE_COMPONENT"/>
    <activity android:name="com.huawei.systemmanager.optimize.process.ProtectActivity"></activity>
    <activity android:name="com.huawei.systemmanager.startupmgr.ui.StartupNormalAppListActivity"></activity>
    <activity android:name="com.huawei.systemmanager.appcontrol.activity.StartupAppControlActivity"></activity>
    
# Check
    mPackageManager = mContext.getPackageManager();
    for (ApplicationInfo appInfo : mPackageManager.getInstalledApplications(PackageManager.GET_META_DATA)) {
       if (appInfo.packageName.equals("com.huawei.systemmanager")) {
         huawei = true;
       }
    }
    
# Call
        Intent intent = new Intent();
        try {
            intent.setComponent(new ComponentName("com.huawei.systemmanager", "com.huawei.systemmanager.optimize.process.ProtectActivity"));
            startActivity(intent);
        } catch (Exception e) {
            log(LOGTAG, "Failed to call com.huawei.systemmanager.optimize.process.ProtectActivity");
            log(LOGTAG, "Trying to use StartupNormalAppListActivity");
            try {
                intent = new Intent().setComponent(new ComponentName("com.huawei.systemmanager",
                        Build.VERSION.SDK_INT >= Build.VERSION_CODES.P ? "com.huawei.systemmanager.startupmgr.ui.StartupNormalAppListActivity" : "com.huawei.systemmanager.appcontrol.activity.StartupAppControlActivity"));
                startActivity(intent);
            } catch (Exception e2) {
                log(LOGTAG, "Failed to call StartupNormalAppListActivity");
            }
        }
