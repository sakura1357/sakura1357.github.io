
# 一、初始化项目及配置
``` bash
# 配置proxy
git config --global http.proxy 10.100.100.101:8080
git config --get http.proxy
npm config set proxy="http://10.100.100.101:8080"
npm config get proxy

# 配置 npm 淘宝源
node --version
npm config set registry https://registry.npm.taobao.org
npm config get registry
npm update

# 安装 hexo-cli 脚手架工具包
npm install hexo-cli -g
# 初始化 hexo 目录
hexo init sakura1357.github.io
cd sakura1357.github.io
# 安装依赖包
npm install
# 启动本地hxeo server
hexo server # http://localhost:4000/

# clone 到 hexo-theme-yun theme/yun/ 目录下
# 创建 source/_data/yum.yaml 自定义主题相关配置
git clone https://github.com/YunYouJun/hexo-theme-yun themes/yun

# 安装 hexo-theme-yun 相关渲染器 pug 和 stylus
npm install hexo-render-pug hexo-renderer-stylus
npm install hexo-deployer-git

# 生成静态文件 public/ 目录下
hexo generate

# 初始化 git 仓库，只需一次
git init
# 创建 hexo 分支用来存储源代码
git checkout -b hexo
# 而默认的 master 分支用来存储生成后的要部署静态文件
# sakura1357.github.io 部署后，GitHub Pages 将默认使用 master 分支作为静态文件部署

# 查看分支
git branch -v

# 安装 hexo-deployer-git 方便部署到 GitHub Pages
# _config.yml 配置相关部署信息
npm install hexo-deployer-git

# 部署到 GitHub Pages， 验证 github 用户名密码
hexo deploy

# 与远程仓库建立链接，只需一次
git remote add origin https://github.com/sakura1357/sakura1357.github.io
# hexo 分支，本地提交
git add -A
git commit -m "message"

# push 到远程仓库hexo分支，第一次提交，需设置一下默认提交分支，后续无需 --set-upstream
git push --set-upstream origin hexo # 后续执行 git push origin hexo 即可

```

# 二、页面配置
> https://yun.yunyoujun.cn/guide/page.html#%E6%96%87%E7%AB%A0
```bash
# 新建自定义页面
# 关于 About
hexo new page about

# 关于站点
# source/about/site.md

# 404
# source/404.md

# 友链 links
#
hexo new page links

```
# 三、写作
```bash
# 安装和配置标签 tags
npm install hexo-generator-tag
# source/tags/index.md 修改 Front Matter
hexo new page tags

# 安装和配置分类 categories
npm install hexo-generator-category
# source/categories/index.md 修改 Front Matter
hexo new page categories

# 新建一篇文章 source/_posts/post_name.md 
hexo new post post_name
```