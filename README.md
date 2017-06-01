# WFBannerView
更改自czy1121/bannerview</br>
源码链接：https://github.com/czy1121/bannerview
如有侵权请联系QQ：747257503，本人将立即删除！ 


横幅广告图片轮播控件</br>

![](https://github.com/czy1121/bannerview/raw/master/screenshot.png)


Gradle 
-----
```Java
repositories { 
    maven { url "https://jitpack.io" }
} 
dependencies {
    compile 'com.github.warmfire:WFBannerView:v1.0.0'
    compile 'com.github.bumptech.glide:glide:4.0.0-RC0'
}
```

Usage 
-----
```Java
<com.warmfire.bannerview.BannerView
    android:id="@+id/banner1"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_marginBottom="20dp"
    android:background="@android:color/white"
    app:bvAspectRatio="0.6666666"
    app:bvIndicatorColor="#cccccc"
    app:bvIndicatorColorSelected="@color/colorAccent"
    />

<com.warmfire.bannerview.BannerView
    android:id="@+id/banner2"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:background="@android:color/white"
    app:bvAspectRatio="0.6666666"
    app:bvBarColor="#88888888"
    app:bvIndicatorColor="#cccccc"
    app:bvIndicatorColorSelected="@color/colorAccent"
    app:bvIndicatorGravity="right"
    app:bvTitleVisible="true"/>
```


Java 
-----
```Java
final BannerView banner1 = (BannerView) findViewById(R.id.banner1);
banner1.setViewFactory(new BannerViewFactory());
banner1.setDataList(list);
banner1.setClickType(0); // 设置点击图片事件，0为Toast，1为页面跳转
banner1.setContext(MainActivity.this); 
banner1.start();
```
 
属性
-----
```Java
<declare-styleable name="BannerView">
    <!-- 是否支持循环, 默认 true -->
    <attr name="bvIsLoop" format="boolean"/>
    <!-- 是否支持自动滚动, 默认 true -->
    <attr name="bvIsAuto" format="boolean"/>
    <!-- 滚动延时, 默认5000ms -->
    <attr name="bvDelay" format="integer"/>
    <!-- 滚动间隔, 默认5000ms -->
    <attr name="bvInterval" format="integer"/>
    <!-- 高宽比(height/width)-->
    <attr name="bvAspectRatio" format="float"/>

    <!-- 底部背景条颜色, 默认透明 -->
    <attr name="bvBarColor" format="color"/>
    <!-- 底部背景条在滚动到最后一个item时是否可见, 默认 true -->
    <attr name="bvBarVisibleWhenLast" format="boolean"/>

    <!-- 底部背景条padding, 默认10dp -->
    <attr name="bvBarPaddingLeft" format="dimension"/>
    <attr name="bvBarPaddingTop" format="dimension"/>
    <attr name="bvBarPaddingRight" format="dimension"/>
    <attr name="bvBarPaddingBottom" format="dimension"/>

    <!-- 标题文字颜色, 默认 #ffffff -->
    <attr name="bvTitleColor" format="color"/>
    <!-- 标题文字大小, 默认 14sp -->
    <attr name="bvTitleSize" format="dimension"/>
    <!-- 标题是否可见, 默认 false  -->
    <attr name="bvTitleVisible" format="boolean"/>


    <!-- 指示器是否可见, 默认 auto  -->
    <attr name="bvIndicatorVisible" format="integer">
        <enum name="auto" value="0"/>
        <enum name="always" value="1"/>
        <enum name="never" value="2"/>
    </attr>

    <!-- 指示器位置, 默认 center-->
    <attr name="bvIndicatorGravity">
        <enum name="center" value="17"/>
        <enum name="left" value="3"/>
        <enum name="right" value="5"/>
    </attr>

    <!-- 指示器项的 宽度/高度/间距, 默认 6dp -->
    <attr name="bvIndicatorWidth" format="dimension"/>
    <attr name="bvIndicatorHeight" format="dimension"/>
    <attr name="bvIndicatorGap" format="dimension"/>

    <!-- 指示器未选中颜色, 默认 #88ffffff  -->
    <attr name="bvIndicatorColor" format="color"/>
    <!-- 指示器选中颜色, 默认 #ffffff -->
    <attr name="bvIndicatorColorSelected" format="color"/>

    <!-- 指示器未选中drawable资源 -->
    <attr name="bvIndicatorDrawable" format="reference"/>
    <!-- 指示器选中drawable资源 -->
    <attr name="bvIndicatorDrawableSelected" format="reference"/>
</declare-styleable>
```

