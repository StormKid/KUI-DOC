## 屏幕适配方案

> 目前常见的适配方式选取了最轻量级别的 “头条适配方式” 

整体代码如下：
```kotlin
    /**
     * 系统的density
     */
    private var sysDensity = 0f
    /**
     * 系统的ScaleDensity
     */
    private var sysScaleDensity = 0f
    fun setCustDensity(application: Application,activity: Activity){
        val displayMetrics = application.resources.displayMetrics
        if (sysDensity==0f){
            sysDensity = displayMetrics.density
            sysScaleDensity = displayMetrics.scaledDensity
            application.registerComponentCallbacks(object :ComponentCallbacks{
                override fun onLowMemory() {

                }

                override fun onConfigurationChanged(newConfig: Configuration?) {
                    if (newConfig!=null&&newConfig.fontScale>0){
                        sysScaleDensity = application.resources.displayMetrics.scaledDensity
                    }
                }

            })
        }
        //重新赋值屏幕密度
        val targetDensity = displayMetrics.widthPixels / selfScreen
        val targetScaleDensity = targetDensity*(sysScaleDensity/sysDensity)
        val dpi = targetDensity*160
        displayMetrics.density = targetDensity
        displayMetrics.densityDpi = dpi.toInt()
        displayMetrics.scaledDensity = targetScaleDensity

        val actDisplayMetrics = activity.resources.displayMetrics
        actDisplayMetrics.density = targetDensity
        actDisplayMetrics.densityDpi = dpi.toInt()
        actDisplayMetrics.scaledDensity = targetScaleDensity
    }
```