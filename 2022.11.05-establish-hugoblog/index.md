# Hugo搭建博客

Hugo搭建博客
<!--more-->
## Hugo搭建博客

### 主题的搭建

1.如果电脑已经安装了Git，可以使用 git 来进行下载

>* 打开 git bash ，切换到博客根目录（HongFree_Blog文件夹中）
>* 执行git clone <https://themes.gohugo.io/themes/vno-hugo/>
>* 下载完成后，主题在E:\HuGo_WorkSpace\HongFree_Blog\themes\Vno目录里面

2.如果未安装 git ，也可以直接下载安装包文件，然后在HongFree_Blog\themes\Vno 中新建 Vno 文件夹（主题文件夹名），将安装包解压到此处即可。
>一般主题都带有示例文件，例如我的这个主题

![这个是我举的栗子](blog_1.png)

>我们将 exampleSite 文件夹中的文件复制到博客根目录（HongFree_Blog文件夹）中，直接覆盖替换。

![这个是我举的栗子](blog_2.png)

>* 这里说明下，不同主题示例中的内容略有不同。在我们的博客站点中 myblog/content/post/xxx.md ,这里是存放你的文章的地方，我们这里把主题文章示例覆盖博客文章来预览。
>* config.toml 为配置文件，后续我们可以进行站点配置（博客地址、构建配置、标题、导航栏等等）。

3.启动hugo服务

>1. 在博客根目录（HongFree_Blog），cmd 执行 hugo server --theme=LoveIt --buildDrafts 来启动站点服务。
>2. 在浏览器中打开地址 <http://localhost:1313/> 查看是否启动成功
--theme : 指定主题
--buildDrafts : 引入 content 中的草稿文件

![这个是我举的栗子](blog_3.png)

## 部署到 GitHub

登录你的 GitHub 账号，创建一个仓库，注意:创建仓库的名称必须是你github的昵称且必须小写再加上.github.io

>例如我的昵称是 Hong-Free，则输入 <http://hong-free.github.io>

1.cmd 切换到根目录下（HongFree_Blog）, 运行 hugo --theme=LoveIt --baseUrl="http://hongfree9.github.io" --buildDrafts
2.会在博客根目录 myblog 生成 public 文件夹，里面就是编译好的静态页面文件。在public目录下：

>* 执行 git init将public文件夹变成 git 本地仓库
>* 执行git add . 将文件夹所以文件放入暂存区
>* 执行git commit -m "my hugoblog" 提交暂存区到本地仓库中
>* 执行git remote add origin <https://github.com/Hong-Free/hong-free.github.io.git> 添加远程版本库
>* 执行git push -u origin master 将本地仓库代码推送到远程库

你就可以获得一个属于自己的blog了
![这个是我举的栗子](blog_4.png)

## 错误

>Error: module "LoveIt" not found; either add it as a Hugo Module or store it in "E:\\HuGo_WorkSpace\\HongFree-Blog\\..themes..".: module does not exist

当出现这个错误的时候，请打开cmd，输入

>* git init
>* git add .
>* git commit -m "first commit"

成功后，再输入

>* hugo server

就可以正常打开网站

