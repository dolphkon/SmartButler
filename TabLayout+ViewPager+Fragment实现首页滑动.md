# 概述
   TabLayout 是 Google 官方在 14 年 Google I/O 大会上推出的一个具有 Material Design 效果的一个控件库，作为一个并标签指示器，它可以与 ViewPager 进行联动，两者配合 Fragment 使用可以实现滑动标签页，就是类似知乎和微信那种。
   # 实现过程
 * 首先我们需要在 app 的 gradle  中添加 design 包的依赖库：
 'compile 'com.android.support:design:25.0.0''
  好，我们来看看主页面 activity_main.xml 的布局文件:
  '<?xml version="1.0" encoding="utf-8"?>'
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent">
    <LinearLayout
        android:id="@+id/linearlay"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:orientation="vertical">
    <android.support.design.widget.TabLayout
        android:id="@+id/mtablayout"
        android:background="@color/colorPrimary"
        app:tabGravity="fill"
        app:tabIndicatorColor="@color/colorAccent"
        app:tabMode="fixed"
        app:tabTextColor="@android:color/white"
        app:tabSelectedTextColor="@color/colorAccent"
        android:layout_width="match_parent"
        android:layout_height="wrap_content">

    </android.support.design.widget.TabLayout>

  <android.support.v4.view.ViewPager
      android:id="@+id/mviewpager"
      android:layout_width="match_parent"
      android:layout_height="0dp"
      android:layout_weight="1">
  </android.support.v4.view.ViewPager>
    </LinearLayout>
</RelativeLayout>'''
 这里需要注意一下，为了实现如效果图中更改标示线的颜色，以及标题的颜色大小，整个TabLayout的背景颜色等等，我们需要在布局的开头添加命名空间
 '''xmlns:app="http://schemas.android.com/apk/res-auto" ''' 
 这里还有一些属性：
   app:tabMode="fixed"     表示顶部的tab布局不可滑动
   app:tabIndicatorColor="@color/colorAccent" 表示顶部Tab 下方那条线的颜色
   app:tabSelectedTextColor="@color/colorAccent" 表示Tab 被选中时候的颜色
   app:tabTextColor="@android:color/white"  表示Tab 未被选中时候的颜色
  
  
