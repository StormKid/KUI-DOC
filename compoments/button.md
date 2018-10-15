## button
!> ** 点击事件的承载者，触发事件来完成对业务逻辑的状态进行处理**

**使用方式：**
> 默认按钮：

```xml
   <com.stormkid.kui_base.button.KuiButton  android:layout_width="@dimen/dp_80"
                                            app:text="默认按钮"
                                            app:text_dimen="@dimen/sp_14"
                                            android:layout_height="@dimen/dp_40"/>

```

> 默认圆形按钮：

```xml
 <com.stormkid.kui_base.button.KuiButton android:layout_width="@dimen/dp_80"
                                            app:bg_drawable="circle"
                                            app:text="默认圆形按钮"
                                            android:layout_margin="@dimen/dp_10"
                                            app:text_dimen="@dimen/sp_10"
                                            android:layout_height="@dimen/dp_80"/>
```
!>**注意：圆形按钮需要指定宽高相等，切勿使用wrap_content**

> 默认圆弧按钮：

```xml
    <com.stormkid.kui_base.button.KuiButton android:layout_width="@dimen/dp_80"
                                            app:bg_drawable="round"
                                            app:text="默认圆弧按钮"
                                            app:text_dimen="@dimen/sp_10"
                                            android:layout_height="@dimen/dp_40"/>
```

> 默认带icon按钮：

```xml
 <com.stormkid.kui_base.button.KuiButton android:layout_width="wrap_content"
                                                app:text="默认按钮"
                                                android:id="@+id/click_right"
                                                app:icon_res="@drawable/ic_home"
                                                app:text_dimen="@dimen/sp_10"
                                                android:layout_height="wrap_content"/>
```

!> **直接输入icon的res即可显示图标按钮**

> Attrs

| AttrName  | Type | DefultValue    | Remark  |
|-------|---|-----------|-------|
| image_dimen  | dimention | 20dp     | 图标宽高 |
| left_image_icon | resource  | 0     | 左图标   |
| left_icon_color  | resource   | white | 左图标颜色     |
| right_image_icon | resource  | 0     | 右图标   |
| right_icon_color  | resource   | white | 右图标颜色     |
| title_text  | string   | "" | 主标题/主显示文字     |
| title_size  | dimention   | 14sp | 主标题/主显示文字字号     |
| title_color  | resource   | #666 | 主标题/主显示文字颜色     |
| title_gravity  | enum   | CENTER | 主标题文字位置【LEFT/RIGHT/CENTER】 |
| content_text  | string    | "" | 小标题文字内容     |
| content_size  | dimention   | true |  小标题文字字体大小    |
| content_color  | resource   | #999 |  小标题文字字体颜色     |
| is_nav_bar  | boolean   | true | 是否是标题栏     |
| is_right_text  | boolean   | false | 是否使用小标题当右侧点击功能按钮 |
------------------------

>效果图：

![button效果图](../editImg/button.png ":size=300x")