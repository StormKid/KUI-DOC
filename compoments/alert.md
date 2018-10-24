## alert
!> **功能弹窗，可以在页面上突出显示你所想要的内容**

>使用方式：

```kotlin
class AlertActivity : MainActivity(),AlertContentListener {
    //在窗口关闭之前可以运行想要的功能
    override fun beforeDismiss() {}
    //在弹窗窗口弹出后，可实现想要数据填充显示，或者窗口控制等，防止了在窗口显示前的调用出现空指针
    override fun contentViewEvents(view: View,dialog: DialogFragment) {
        view.findViewById<View>(R.id.yes).setOnClickListener { dialog.dismiss() }
    }
    override fun getLayoutId(): Int = R.layout.alert_sample
    override fun initView() {
        show_normal_alert.setOnClickListener {
             KuiAlert.instance(DialogModel(R.layout.alert_self_content, 0),this)
                     .show(supportFragmentManager,"tag")
        }
    }
```
** 说明：**

可以在默认所有的activity或fragment中进行构建，构建必须实现**AlertContentListener**来完成回调任务。其使用的核心API为：
```kotlin
KuiAlert.instance(DialogModel,AlertContentListener)
```

DialogModel为输入给alert的对象，实现参数传递，其api为：

``` kotlin
/**
 * 自定义alert 构建对象
 * @param  layoutId 自定alert填充布局
 * @param  styleId 自定义alert xml属性样式
 */
data class DialogModel(@LayoutRes val layoutId:Int,@StyleRes val styleId:Int)
```

可以注入任意的布局文件，以及任意的style，来自主的构建自己想要的alert。

> **KuiChooseAlert**

**说明：KuiChooseAlert为KuiAlert 的自定义双按钮方案，其图如下图所示：**

![alert_two_button](../editImg/alert_two_button.png)

**使用初始化**

```kotlin
//普通初始化显示
KuiChooseAlert.instance
                .setTitle("标题")
                .setContent("提示内容")
                .initCallback({
                 //确定回调
                        },{
                 //取消回调
                        }).build().show(supportFragmentManager,"flag")


//全套初始化显示
 KuiChooseAlert.instance
                    .setTitle("title")
                    .setContent("content")
                    .setTitleColor(Color.GRAY)
                    .setContentColor(Color.LTGRAY)
                    .setPositiveButtonColorful(ColorResButton())
                    .setNegativeButtonColorful(ColorResButton())
                    .setNegativeText("cancel")
                    .setPositiveText("okay")
                    .initClickDismiss(true)
                    .initCallback({
                        //确定回调
                         },{
                        //取消回调
                    }).build().show(supportFragmentManager,"tag")


```