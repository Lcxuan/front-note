## HTML

- Hyper Text Markup Language （超文本标记语言）

- HTML 通过标签来标记要显示的网页中的各个部分。网页文件本身是一个文本文件，通过在文本文件中添加标记符，可以告诉浏览器如何显示其他其中的内容（如：文字如何处理、画面如何安排）
  
  ```html
  <!DOCTYPE html> <!-- 约束，声明 -->
  <html lang="en"> <!-- html标签表示html的开始 lang="en" 表示语言 -->
  <head>  <!-- 表示头部信息，一般包含三个部分内容：title标签, css样式, js代码 -->
      <meta charset="UTF-8"> <!-- 表示当前页面使用UTF-8字符集 -->
      <title>Title</title> <!-- 表示标题 -->
  </head>
  <body> <!-- body标签是整个html页面显示的主体内容 -->
      <input /> <!-- 子结束标签 -->
  </body>
  </html>
  ```

### 注释

- 注释中的内容会被浏览器所忽略，不会在网页中直接显示，但是可以在源码中查看到
  
  ```html
  <!-- 这是一个注释 -->
  ```

### 标签中的属性

- 在标签中（开始标签或者子结束标签）可以设置属性，采用键值对形式

- 在标签内使用属性时，需要使用空格隔开

- 属性名不能随便写，根据文档中的规定来编写

- 有些属性是有属性名，有些是没有的，如果有属性值，使用引号（单 / 双）引起来

- 标签中可以有多个属性，多个属性之间使用空格隔开
  
  ```html
  <h1>这是<font color="red">属性</font></h1>
  ```

### 文档声明

- 用来告诉浏览器当前网页的版本

- html5的文档声明
  
  ```html
  <!DOCTYPE html>
  ```

### 字符编码

- 可以通过 <meta> 标签来设置网页的字符集，避免乱码问题
  
  ```html
  <meta charset="utf-8">
  ```

### 实体（转义字符）

- 在网页中编写多个空格时，默认情况下会自动解析为一个空格

- 实体的语法：&实体的名字;
  
  ```html
       代表一个空格
  >      大于号
  <      小于号
  ©    版权
  ```

### meta标签

- 主要用于设置网页的一些元数据，元数据不是给用户看的
  
  - charset：指定网页的字符集
  
  - name：指定数据的名称
    
    - keywords：表示网站的关键字，可以同时执行多个关键字，关键字之间使用 "," 隔开
    
    - description：用于指定网站的描述，会显示在搜索引擎的结果中
  
  - content：指定数据的内容
  
  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <meta name="keywords" content="HTML5,CSS3">
      <meta name="description" content="这是一个非常不错的网站">
      <title>Title</title>
  </head>
  <body>
  
  </body>
  </html>
  ```

### 语义化标签

#### 标题标签

- h1 ~ h6：一共有六级标题

- 一般情况下一个页面中只会有一个标题标签

- 一般情况下标题标签只会使用到 h1 ~ h3

- 标题标签是一个块元素
  
  ```html
      <h1>一级标题</h1>
      <h1>二级标题</h1>
      <h1>三级标题</h1>
      <h1>四级标题</h1>
      <h1>五级标题</h1>
      <h1>六级标题</h1>
  ```

- hgroup标签：用来标签分组，可以将一组相关的标题同时放入到hgroup中
  
  ```html
      <hgroup>
          <h1>标题</h1>
          <h2>描述</h2>
      </hgroup>
  ```

#### P标签

- 表示页面中的一个段落

- P标签也是一个块元素
  
  ```html
  <p>这是一个段落</p>
  ```

#### em标签

- 将文本变斜

- em标签是一个行内元素
  
  ```html
  <p>今天天气<em>真</em>不错</p>
  ```

#### strong标签

- 将文本加粗

- strong标签是一个行内标签
  
  ```html
  <p>你今天<strong>必须</strong>完成作业</p>
  ```

#### blockquote标签和q标签

- blockquote标签表示一个长引用，q标签表示一个短引用

- blockquote标签是一个块元素

- q标签是一个行内元素
  
  ```html
      鲁迅说：
      <blockquote>
          这句话我没有说过
      </blockquote>
  
      子曰<q>学而时习之，乐呵乐呵!</q>
  ```

#### br标签

- br标签表示页面中换行
  
  ```html
  今天<br>天气真不错
  ```

#### header标签、main标签和footer标签

- header标签：表示网页的头部

- main标签：表示网页的主体部分（一个页面中只会有一个main）

- footer标签：表示网页的底部
  
  ```html
  <body>
      <header></header>
      <main></main>
      <footer></footer>
  </body>
  ```

#### nav标签

- 表示网页中的导航
  
  ```html
  <nav></nav>
  ```

#### aside标签

- 表示一个侧边栏
  
  ```html
  <aside></aside>
  ```

#### article标签

- 表示一个独立的文章
  
  ```html
  <article></article>
  ```

#### section标签

- 表示一个独立的区块
  
  ```html
  
  ```

#### div标签【重要】

- 没有语义，用来表示一个区块
  
  ```html
  <div></div>
  ```

#### span标签

- 没有语义，一般用于在网页中选中文字
  
  ```html
  <span></span>
  ```

### 块元素和行内元素

- 块元素
  
  - 在网页中一般通过块元素来对页面进行布局
  
  - p标签中不能放任何块元素
  
  - 一般情况下，块元素基本上什么都可以放

- 行内元素
  
  - 主要用来包裹文字
  
  - 一般情况下会在块元素中放行内元素，不会在行内元素中放块元素

### 列表

分为三种：有序列表、无序列表和定义列表

#### 有序列表

- 使用ul标签来创建有序列表，使用li标签来表示列表项
  
  ```html
      <ul>
          <li>Java</li>
          <li>PHP</li>
          <li>Python</li>
      </ul>
  ```

#### 无序列表

- 使用ol标签来创建无序列表，使用li标签来表示列表项
  
  ```html
      <ol>
          <li>Java</li>
          <li>PHP</li>
          <li>Python</li>
      </ol>
  ```

#### 定义列表

- 使用dl标签来创建一个定义列表，使用dt来表示定义的内容，使用dd来对内容进行解释说明
  
  ```html
      <dl>
          <dt>结构</dt>
          <dd>结构表示网页的结构</dd>
      </dl>
  ```

### 超链接

- 使用 a 标签来定义超链接，可以从一个页面跳转到其他页面，或者是当前页面的其他位置

- 使用 href 属性来指定跳转的目标路径
  
  - 可以是一个外部网站的地址
  
  - 也可以是一个内部页面的地址
  
  - 设置为 # ，点击超链接后页面不会发生跳转，而是跳到当前页面的顶部
  
  - 可以跳转到当前页面的指定位置，只需设置 #目标元素的id属性值
  
  - 可以使用 javascript:; 来作为href属性的值，此时点击什么效果都不会发生

- target属性，用来指定超链接打开的位置
  
  - __self：默认值，在当前页面打开超链接
  
  - __blank：在一个新的页面中打开超链接

- id属性，唯一不重复的
  
  - 每个标签都可以添加一个id属性
  
  - 页面中不能出现重复的id属性

- a 标签是一个行内元素

- a 标签中可以嵌套任何元素，除了自身外
  
  ```html
  <a href="http://www.baidu.com">百度</a>
  <a href="./demo1.html">内部页面</a>
  <a href="http://www.baidu.com" target="_blank">百度一下</a>
  ```

### 图片标签

- 用于向当前页面中引入一个外部图片，使用img标签来引入外部图片

- img标签是一个自结束标签

- src 属性指定的是外部图片的路径
  
  - 可以指定的是外部图片的路径
  
  - 也可以是内部图片的路径

- alt属性是对图片的描述，默认情况下不会显示，有些浏览器会在图片无法加载时显示
  
  - 搜索引擎会根据alt中的内容来识别图片

- width属性和height属性
  
  - width属性：图片的宽度
  
  - height属性：图片的高度

- img标签属性一种替换元素（基于块和行内元素之间）
  
  ```html
  <img src="image.jpg" alt="背景">
  ```

### 内联框架

- 用于向当前页面中引入一个其他页面

- 使用 iframe标签 来创建一个内联框架

- src 属性：指定要引入的网页路径

- frameborder 属性：用于指定内联框架的边框
  
  ```html
  <iframe src="https://www.baidu.com" frameborder="0"></iframe>
  ```

### 音视频

#### audio标签

- 用来向页面中引入一个外部的音频文件 

- controls 属性：是否允许用户控制播放，不加则不允许

- autoplay 属性：是否自动播放，不加则手动播放，但是大部分浏览器都不会自动播放

- loop 属性：是否循环播放

- 除了通过src来指定外部文件的路径外，还可以通过source来指定文件的路径
  
  ```html
  <audio src="audio.mp3" controls autoplay loop></audio>
  
  <audio controls>
      <source src="audio.mp3">
  </audio>
  ```

#### video标签

- 向网页中引入一个视频文件

- 使用方式和audio标签一样
  
  ```html
  <video src="video.mp4" controls></video>
  ```

### 表格

- 通过<table>标签来创建表格

- 在表格中，使用 <tr> 标签表示一行，在 <tr> 标签中使用 <td> 标签表示一个单元格

- `<td>`标签属性：
  
  - colspan属性：横向合并单元格
  
  - rowspan属性：纵向合并单元格
  
  ```html
      <table border="1">
          <tr>
              <td>姓名</td>
              <td>年龄</td>
          </tr>
          <tr>
              <td>张三</td>
              <td>18</td>
          </tr>
          <tr>
              <td colspan="2">合并单元格</td>
          </tr>
      </table>
  ```

- 长表格使用 <thead> 标签、<tbody> 标签和 <tfoot> 标签，可以分为三个部分：
  
  - 头部
  
  - 主体
  
  - 底部
  
  ```html
      <table>
          <thead>
              <tr>
                  <td>日期</td>
                  <td>收入</td>
                  <td>支出</td>
                  <td>合计</td>
              </tr>
          </thead>
          <tbody>
              <tr>
                  <td>2000.1.1</td>
                  <td>500</td>
                  <td>100</td>
                  <td>400</td>
              </tr>
              <tr>
                  <td>2000.1.1</td>
                  <td>500</td>
                  <td>100</td>
                  <td>400</td>
              </tr>
              <tr>
                  <td>2000.1.1</td>
                  <td>500</td>
                  <td>100</td>
                  <td>400</td>
              </tr>
              <tr>
                  <td>2000.1.1</td>
                  <td>500</td>
                  <td>100</td>
                  <td>400</td>
              </tr>
          </tbody>
          <tfoot>
              <tr>
                  <td></td>
                  <td></td>
                  <td>合计：</td>
                  <td>1600</td>
              </tr>
          </tfoot>
      </table>
  ```

### 表单

- 用于将本地的数据提交给远程的服务器

- 使用form标签来创建一个表单，必要属性
  
  - action属性：表单要提交的服务器地址

- 表单项
  
  - 文本框：<input type="text">
  
  - 密码框：<input type="password">
  
  - email框：<input type="email">
  
  - 提交按钮：<input type="submit">
  
  - 单选按钮：<input type="radio">
    
    - 需要指定value属性，用于作为返回到服务器的值
    
    - checked属性，可以将单选按钮设置为默认选中
  
  - 多选框：<input type="checkbox">
    
    - 使用方式和单选按钮一样
  
  - 下拉列表
    
    ```html
    <select name="select">
        <option value="选项">选项一</option>
    </select>
    ```
  
  - 普通按钮：<input type="button">
  
  - 重置按钮：<input type="reset">
  
  - 

- **注意：如果数据要提交到服务器中，必须要为表单项指定一个name属性值**

- autocomplete属性，表示是否自动补全

- readonly属性，将表单项设置为只读，数据会提交

- disabled属性，将表单项设置为禁用状态，数据不会提交

- autofocus属性，设置表单项自动获取焦点
