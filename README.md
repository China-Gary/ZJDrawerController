# ZJDrawerController

一个使用方便的侧滑测单, 抽屉菜单, 支持四种打开和关闭的动画, 支持缩放, 可以设置打开的手势的位置, 可以设置在那些页面可以打开抽屉菜单

![drawer1.gif](http://upload-images.jianshu.io/upload_images/1271831-6766ab3ea92d787c.gif?imageMogr2/auto-orient/strip)


![drawer2.gif](http://upload-images.jianshu.io/upload_images/1271831-cab8b7bafe5dd255.gif?imageMogr2/auto-orient/strip)


```
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    ZJLeftViewController *left = [ZJLeftViewController new];
    
    ZJCenterViewController *center = [ZJCenterViewController new];
    
    UINavigationController *navi = [[UINavigationController alloc] initWithRootViewController:center];
    
    ZJRightViewController *right = [ZJRightViewController new];
    
    ZJDrawerController *drawer = [[ZJDrawerController alloc] initWithLeftController: left centerController:navi rightController:right];
    
    // 背景图片
    drawer.backgroundImage = [UIImage imageNamed:@"1"];
    // 动画类型
    drawer.drawerControllerStyle = ZJDrawerControllerStyleParallaxSlide;
    // 任何界面都能打开抽屉
    drawer.canOpenDrawerAtAnyPage = YES;
    //...
    self.window = [[UIWindow alloc] initWithFrame:[UIScreen mainScreen].bounds];
    self.window.backgroundColor = [UIColor whiteColor];
    self.window.rootViewController = drawer;
    [self.window makeKeyAndVisible];
    
    return YES;
}
```

> 这是我写的<iOS自定义控件剖析>这本书籍中的一个demo, 如果你希望知道具体的实现过程和其他的一些常用效果的实现, 那么你应该能轻易在网上下载到免费的盗版书籍. 

> 当然作为本书的写作者, 还是希望有人能支持正版书籍. 如果你有意购买书籍, 在[这篇文章中](http://www.jianshu.com/p/510500f3aebd), 介绍了书籍中所有的内容和书籍适合阅读的人群, 和一些试读章节, 以及购买链接. 在你准备[购买](http://www.qingdan.us/product/13)之前, 请一定读一读里面的说明. 否则, 如果不适合你阅读, 虽然书籍售价35不是很贵, 但是也是一笔损失.


> 如果你希望联系到我, 可以通过[简书](http://www.jianshu.com/users/fb31a3d1ec30/latest_articles)联系到我

