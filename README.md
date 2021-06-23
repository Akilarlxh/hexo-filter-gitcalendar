# hexo-filter-gitcalendar

给`hexo`添加 [首页git提交日历](https://akilar.top/posts/1f9c68c9/)

# 安装

1. 安装插件,在博客根目录`[Blogroot]`下打开终端，运行以下指令：
  ```bash
  npm install hexo-filter-gitcalendar --save
  ```

2. 添加配置信息，以下为写法示例
  在站点配置文件`_config.yml`或者主题配置文件`_config.butterfly.yml`中添加

  ```yaml
  # hexo-filter-gitcalendar
  # see https://akilar.top/posts/1f9c68c9/
  gitcalendar:
    enable: true # 开关
    priority: 5 #过滤器优先权
    enable_page: / # 应用页面
    layout: # 挂载容器类型
      type: id
      name: recent-posts
      index: 0
    user: Akilarlxh #github用户名
    api: 'https://python-github-calendar-api.vercel.app/api'
    pc_minheight: 280px #桌面端最小高度
    mobile_minheight: 0px #移动端最小高度
    color: "['#e4dfd7', '#f9f4dc', '#f7e8aa', '#f7e8aa', '#f8df72', '#fcd217', '#fcc515', '#f28e16', '#fb8b05', '#d85916', '#f43e06']" #橘黄色调
    # color: "['#ebedf0', '#fdcdec', '#fc9bd9', '#fa6ac5', '#f838b2', '#f5089f', '#c4067e', '#92055e', '#540336', '#48022f', '#30021f']" #浅紫色调
    # color: "['#ebedf0', '#f0fff4', '#dcffe4', '#bef5cb', '#85e89d', '#34d058', '#28a745', '#22863a', '#176f2c', '#165c26', '#144620']" #翠绿色调
    # color: "['#ebedf0', '#f1f8ff', '#dbedff', '#c8e1ff', '#79b8ff', '#2188ff', '#0366d6', '#005cc5', '#044289', '#032f62', '#05264c']" #天青色调
    container: #父元素容器，需要使用pug语法
  ```
3. 参数释义

  |参数|备选值/类型|释义|
  |:--|:--|:--|
  |priority|number|【可选】过滤器优先级，数值越小，执行越早，默认为10，选填|
  |enable|true/false|【必选】控制开关|
  |enable_page|path/all|【可选】填写想要应用的页面的相对路径（即路由地址）,如根目录就填'/',分类页面就填'/categories/'。若要应用于所有页面，就填'all'，默认为all|
  |layout.type|id/class|【可选】挂载容器类型，填写id或class，不填则默认为id|
  |layout.name|text|【必选】挂载容器名称|
  |layout.index|0和正整数|【可选】前提是layout.type为class，因为同一页面可能有多个class，此项用来确认究竟排在第几个顺位|
  |user|text|github或gitee用户名|
  |api:|url|可以使用提供文档提供的api，也可以考虑自建api，参考教程：[自建API部署](https://akilar.top/posts/1f9c68c9/#自建API部署)|
  |pc_minheight|280px|桌面端最小高度，默认为280px|
  |mobile_minheight|0px|移动端最小高度，默认为0px|
  |color|list|一个包含11个色值的数组，文档给出了四款预设值|
  |container|pug|预留的父元素容器，用以适配多主题，需要用pug语法填写|
# 截图
  ![](https://cdn.jsdelivr.net/npm/hexo-filter-gitcalendar/assets/gitcalendar.png)
