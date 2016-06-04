## 我的个人博客
react小项目，前端使用的material-ui＋react＋redux＋react-router
## 目前只给出react代码
因为后台用的sails，然而写sails的时候，并没有意识到要用git所以等部署带服务器上的时候再说吧
## 加载动画要不要？
其实我也一直在纠结要不要加载中的动画，等考虑好了再更新
## state设计
* pagination,分页
* articleList,文章列表
* messages,留言
* article,文章详情
* comment,评论
* category,分类，包括右侧最新文章以及左侧分类
* resState,响应状态，暂时还没决定要不要，用于保存后台数据响应状态

曾今也疑惑过是要把所有数据都保存，还是只存当前状态，最终还是选择了后者，毕竟我不是做本地存储，而且保存所有无疑是增加自己的负担。

当然如果要保存全部数据的话，推荐使用normalizr来范式化state

## 遇到的坑

### 1、state
关于state的设计是个大坑，可是如果只保存当前状态的话，就方便好多，因为一个窗口只需要展示一篇文章，或者文章列表，或者留言，
一遍文章只对应一遍文章的评论，

个人的感觉就是：保存当前状态，减少了前端对数据的处理，简化了state，让state真正成为一个保存
状态的容器，而不是存储数据的容器，也不用太多的考虑范式化（state就是指状态，如果用来‘存数据’那不是把数据库的活再做了一遍，这
不科学）

### 2、route和state
在某篇文章上看到过，route和state存在不对称的问题，我当时想到的是，通过props的params来达到两者的一致，暂时就这样解决吧，作者
也没有给出可行的方案

### 3、待更新...