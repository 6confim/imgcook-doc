# 阿里 imgcook 使用整理

## 可行性

为什么使用imgcook生成移动页面是可以做到的？

1. 移动页面通常布局是通栏布局，相对简单
2. 移动页面可以概括为文字、图片
3. 适配简单，通常就是适配屏幕的大小，结构不会变化，并且有比较成熟适配方案（rem）
4. 检测出通栏元素，通栏内的元素相对通栏布局就可以了

## 注意点

1. 分组
    1. UI内容尽量根据通栏进行分组
    2. 设计内的分组要清晰
2. 组件化
    1. 页面内的内容要以块来分组件
    2. 一个页面要尽量拆成多个组件
3. 相对布局
    1. 通栏的内容是相对通栏进行布局的
4. 合并
    1. 需要输出一张图的地方进行使用 `-合并` 输出为一张图，防止出现很多无意义的节点


## 流程

拿 sketch 来举例：

sketch通过插件-生成json文件（该文件对生成dsl文件没有太大的帮助），把改文件上床到imgcook server， imgcook-server生成对应的dsl文件，包括vue、json、jsx、html等，可以是px或者rem的布局等

## 设计注意点
1. 要有模块思维方式
2. 要注意分层（背景，模块内容）
3. 组件合并
4. 如果设计内容超过了设计的边界，使用 mask 或者 直接截图放置，mask

## 前端注意点
1. 模板和组件，做到sketch生成的dsl作为参数传给已有组件
2. 尽量做到自动生成，总计问题反馈给UI
3. 做到路由的自动映射，保证页面自动生成完成后就可以直接上线

## 问题总结
1. 对于块内的元素，大部分使用 position: absolute 布局，这个也没啥问题，希望能改进
2. UI原始文件超过一屏的时候，使用mask，有时候可能会有问题
3. 边框有时候会被莫名其妙丢弃
4. 多行文本尽量使用多个文本
5. 在使用ps mac的时候，会比较慢卡（可能是我的mac），并且效果非常不理想（生成的图乱七八糟的）










