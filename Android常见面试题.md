# Android 常见面试题

## 四大组件
#### Activity
1. onNewIntent()的调用时机

2. 启动模式

3. Activity 的内部机制

4. Activity 的冷启动流程

5. AMS 的作用

6. a-b-c界面，其中b是singleinstance的，那么c界面点back返回a界面，为什么？怎么管理栈的？\

7. 在oncreate里面可以得到view的宽高吗？

8. 从framework 的角度将 activity 的启动流程（冷启动）

9. 为什么要 引入 activity 这个组件？

10. a启动b，b启动c,怎么样可以在c界面点back返回到a？

11. 在 SingleTop 模式中，如果打开一个已经存在栈顶的 Activity，他的生命流程是怎样的？ onPause() -> onNewIntent() -> onResume()

12. ActivityA -> Activity B -> Activity A ，Activity A 启动模式为 singleTask ，Activity B 启动模式为常规模式，问  A 启动 B，B 又启动 A 的生命周期调用顺序？

    启动 A：A onCreate() -> A onStart() -> A onResume()

    A 启动 B：A onPause() -> B onCreate() -> B onStart() -> B onResume() -> A onStop()

    B 又启动 A：B onPause() -> A onNewIntent() -> A onRestart() -> A onStart() -> A onResume() -> B onStop() -> B onDestory() 

#### BroadcastReceive
1. 广播有几种？广播是观察者模式？跨进程广播也是观察者模式吗？
2. 两个应用同时注册一个广播，优先级都一样，哪个会先收到广播？（有序广播？）


#### Service
1. bindService 和 startService 生命周期有啥不同？


#### ContentProvider
1. contentprovider 怎么升级维护
2. contentprovider 已经是进程间通信，为什么还要引入 broadcastreceiver？

## fragment
1. fragment 的基本知识
2. fragment 与 Activity 的对比
3. DialogFragment

## UI
1. RecyclerView 与 ListView 的对比
2. adapter 的泛型和不指定参数数量的优化
3. Android 自定义 View 或者自定义 ViewGroup 的一般步骤
4. Android 的视图层级优化
5. 如何显示 git 图片
6. 滑动控件的深度优化
7. 图表
8. view 的事件分发机制？滑动冲突怎么解决？
9. 自定义 view 的原理和流程？
10. LinearLayout 的布局流程？
11. view 的getWidth和geimeasurewidth有啥区别？
12. view的绘制流程
13. viewpager嵌套滑动冲突怎么解决？
14. 阅读界面书架用什么控件实现？布局怎么做到每行的文字左右对齐？
15. 直播界面，微信对话界面实现？
16. Android:gravity和android:layout_gravity的区别？
17. assets与res/raw的区别？
18. 解释layout_weight的作用，view如何刷新？
19. android常用布局及排版效率？
20. recyclerView 缓存机制相比 listView 缓存机制有啥改进？
21. constainlayout
22. bitmap 有几种格式，分别占多少字节？
23. 系统进程可以用 webview 吗？
24. 计算 viewgroup 的层级，递归实现和非递归实现
25. Bitmap resize 相关 (设置 option 然后 decode)

## 解析xml
1. sax解析xml的优点

## 动画
1. animation.animationlistener干什么用？
2. 属性动画画一个抛物线怎么弄？
3. svg 动画
4. animation 和 animator 的用法，概述实现原理
5. 补件动画常见的效果？有哪几个常见的插入器？
6. 补间动画 click 事件还在原位怎么解决？

## Android 源码分析
1. 主线程使用 Handler 的过程
2.  AsyncTask 和 Handler + Thread 机制的区别
3. 事件的处理机制
4. Handler、Message、Looper 的原理
5. Handler,looper,messagequeue,thread,message,每个类功能、关系？
6. 有哪些多进程通信方式？Binder机制？
7. ams是怎么找到启动的那个activity的？
8. android 事件分发机制
9. Contentvalue键值类型
10. androidvm的进程与linux的进程说法？
11. override与ovrtload的区别？overload的方法是否可以改变返回值的类型？
12. sleep与wait有什么区别？
13. 在android中，请简述jni的调用过程？请结束android.mk的作用，并试写一个android.mk文件（包含一个.c源文件即可）
14. binder 的原理与机制
15. 原子类的了解一个app多进程的好处
16. 主线程 looper 如果没有消息，就会阻塞在那，为什么不会anr？
17. 自己写一个应用，包名就叫 android 行不行，为什么不行？
18. 主线程 Looper 一直循环查消息为何没卡主线程？
19. 用MultiDex解决何事？其根本原因在于？Dex如何优化？主Dex放哪些东西？主Dex和其他Dex调用、关联？Odex优化点在于啥？Dalvik和Art虚拟机区别？多渠道打包如何实现（Flavor、Dimension应用）？从母包生出渠道包实现方法？渠道标识替换原理？
20. Android 打包哪些类型文件不能混淆？

#### okHttp
1. okHttp 有哪些拦截器
2. okhttp 有什么优秀的设计模式？builder 模式有什么好处？责任链模式有什么好处？

#### RxJava

#### zxing
1. zxing 二维码开源框架流程
2. zxing 有过优化提高识别率吗？

#### Glide
1. Glide 缓存特点。

#### 第三方开源数据库



## 适配
1. 为了适配多分辨率，引入什么开源框架？

## 安全
1. 数据加密
2. 代码混淆
3. WebView/Js调用
4. https

## 数据库
1. sqlite 可以执行多线程操作吗？如何保证多线程操作数据库的安全性
2. 数据库的使用
3. 隔代数据库升级
4. shareprefrence 不是进程安全，假设一个 apk 两个进程同时修改 shareprefrence 怎么办？
5. shareprefrence 原理？是否线程安全和进程安全？

## 优化
#### 内存优化
1. 造成内存泄漏的情况有哪些
2. 自定义 Handler 时如何避免内存泄漏
3. ANR 出现的场景及解决方案
4. 怎么分析内存泄漏

#### APK 瘦身

#### 电量优化

#### 布局优化

#### 流畅性优化
1. 怎么评测是否流畅（GPU程序模式）
2. 工具或者技巧（腾讯GT 插件的SM指标，用了 TraceView、Systrace、Hierarchy Viewer 等等）
3. 哪些情况会导致卡顿？（FPS、垂直同步的原理）

#### 网络优化

#### 一个app如果性能不好，怎么分析？

#### 性能优化怎么弄？
1. 避免内存泄漏，为什么说handler用成员内部类会内存泄漏？activity不是已经到gcroot被切断了吗？还有静态context持有activity的引用会内存泄漏，必须要持有怎么办？（及时释放）

## 混淆
2. 为什么要使用代码混淆

## 线程与进程
1. 线程间通信和进程间通信有什么不同
2. 进程切换时需要保存哪些东西（进程上下文）
3. 如果一个app存在多进程，请列出全部的ipc方法
4. 操作系统中进程和线程有什么联系和区别，系统什么时候会在用户态和内核态中切换？如何加载ndk库？如何在jni中注册native函数，有几种注册方式？
5. 一个app启动页另开一个进程，启动页 10s后启动mainactivity，请问5s的时候有几个进程？

## 研发工具
1. IDE
2. 模拟器
3. 网络代理
4. 日志

## 架构
1. 模块化怎么做的？怎么设计的？接口发现暴露怎么做？基于什么思想？MVC、MVP、MVVM 应用和彼此本质区别？


## 其他
1. Android 的打包流程？apk里有哪些东西？签名算法的原理？
2. 了解哪些插件化技术？
3. Android 怎么做保活？
4. 动态代理静态代理区别？
5. MessageQueue 会不会阻塞 UI 线程


## 平时开发遇到的系列问题记录
1. app闪退的原因有哪些？每种情况简述分析过程？
2. 如何避免out of menmory 和 anr?

## 面试准备书籍推荐
1. 《Android开发艺术探索》 任玉刚
2. 《Android 进阶之光》刘望舒
3. 《Android 进阶解密》 刘望舒
4. 《深入理解 Java 虚拟机》 周志明
5. 《Android 源码设计模式》 何红辉 关爱明
6. 《深入理解 Android 内核设计思想》 林学森
