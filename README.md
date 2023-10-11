# ifoxdoc 开发文档
## 克隆本项目
git clone https://github.com/InspireFunction/ifoxdoc.git

现在github推荐用ssh的方式进行操作，具体的可以看下github的文档，现在都是中文的
## 修改

### 修改说明文件
- 打开项目主目录下的 articles 文件夹
- 将要添加的说明做成md格式的文件保存到 articles 文件夹
- 编辑 toc.yml 文件，用编辑器打开进行编辑
- 在文件的末尾添加 格式如下：
  ```
  - name: 你的文件名
    href: 你的文件名.md
  ```
- 保存

toc.yml 文件内容的顺序可以调整，也可以删除，插入等，只要保证每个文件都是一个 name和一个href就可以。

### 修改api文档
- 打开项目主目录下的 src 文件夹
- 将下面四个文件复制到文件夹里，直接替换就可以
  ```htm
  IFox.Basal.dll
  IFox.Basal.xml
  IFox.CAD.ACAD.dll
  IFox.CAD.ACAD.xml
  ```
### 修改主页说明
- 打开本项目主目录下的 index.md 文件
- 编辑后保存即可

### 修改主页顶部的便签
- 打开本项目主目录下的 toc.yml 文件
- 进行修改，举例来说如果要增加一个标签的话，就需要在主目录里新建个文件夹，文件夹的内容就是你要在这个标签下显示的，以articles文件夹为例：
在 toc.yml 文件里 添加：
  ```
  - name: IFoxCAD说明
    href: articles/
  ```
  就说明可以在标签里显示 **IFoxCAD说明** 的内容，然后这个顺序是可以调整的，只要保证name和href一成对的就可以

## 编译
在项目文件夹里打开终端，运行如下命令：

`docfx docfx.json --serve`

编译完成后会提示：
```
Completed building documents in 107855.4454 milliseconds.
Serving "C:\Users\vic\source\repos\docfx_project\_site" on http://localhost:8080. Press Ctrl+C to shut down.
```
这时候就可以直接在浏览器打开 http://localhost:8080 这个网址查看效果。在打开这个网址的时候不要关闭终端。

## 提交
确认没有问题之后，就提交到远程仓库，github action 会自动进行编译并将要显示的内容合并到 gh-pages 分支，github会继续自动将 gh-pages 分支的内容编译为可以显示的静态博客，然后在 [ifoxdoc](https://inspirefunction.github.io/ifoxdoc/) 这个页面显示。

由于github要自动编译需要时间，还有页面数据刷新也需要时间，因此会有一定的时间延迟，过几分钟就会显示新的页面了。