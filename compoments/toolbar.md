## toolbar

!> ** 一种简易多功能条目，可以变成navbar也可以直接使用在项目中**

**使用方式：**
> 标题栏

```xml
 <com.stormkid.kui_base.toolbar.KuiToolBar android:layout_width="match_parent"
                                            app:title_text="我是默认标题栏"
                                            android:background="@color/colorPrimary"
                                            app:title_color="@android:color/white"
                                            app:left_image_icon="@drawable/ic_back"
                                            android:layout_height="@dimen/dp_40"/>
```    

> 条目工具栏

```xml
  <com.stormkid.kui_base.toolbar.KuiToolBar android:layout_width="match_parent"
                                              app:title_text="我是默认使用栏目"
                                              android:background="@color/colorPrimary"
                                              android:id="@+id/tool_title"
                                              app:title_gravity="LEFT"
                                              app:toolbar_ripple_color="@android:color/white"
                                              app:title_color="@android:color/white"
                                              app:is_nav_bar="false"
                                              app:content_text="我是小标题显示内容"
                                              app:content_color="@android:color/white"
                                              app:right_image_icon="@drawable/ic_right"
                                              android:layout_height="@dimen/dp_40"/>
```

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
| toolbar_ripple_color | resource | argb(120,0,0,0) | 点击水波纹颜色 |

> Fun

| FunctionName|Params  | ParamsType    | Remark  |
|-------|-----|------|-------|
| setOnToolClickListener| listener  | OnClickListener    | 整个条目点击  |
| setLeftIconClickListener| listener  | OnClickListener    | 左侧图标点击事件，如果为navbar则此事件默认为finish当前页面，如想自定义可先使用is_nav_bar="false"。  |
| setRightIconClickListener| listener  | OnClickListener    | 右侧图标点击事件  |
| setRightTextClick| listener  | OnClickListener    | 当is_right_text="true"的时候控制右侧小标题文字点击事件  |
| setTitle | titleText  | String    | 设置大标题  |
| setContent | contentText  | String    | 设置小标题  |
| setLeftIcon | icon  | @DrawableRes Int    | 设置左图标 png/jpg调用 |
| setRightIcon | icon  | @DrawableRes Int    | 设置右图标 png/jpg调用 |
| setLeftIconResColor | res, color  | @DrawableRes Int , @ColorRes Int   | 设置左图标和图标颜色 svg调用 |
| setRightIconResColor | res, color  | @DrawableRes Int ,@ColorRes Int   |  设置左图标和图标颜色 svg调用 |
| setTitleColor | color  | @ColorRes Int    | 设置主标题字体颜色 |
| setTitileSize | size  | Float    | 设置主标题字体大小 |
| setContentColor | color  | @ColorRes Int    | 设置副标题字体颜色 |
| setContentSize | size  | Float    | 设置副标题字体大小 |
| setRippleColor | color | @ColorInt Int | 设置水波纹颜色 |

------------------------

!> **如果icon的图标不是svg图像，是png或jpg的话icon color是无法指定颜色的**

>效果图

 ![toolbar效果图](../editImg/toolbar.gif ":size=300x")
