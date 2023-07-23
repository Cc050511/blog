---
title: mkdocs' guidance
date: 2023-07-23 23:08:06
categories:
    - tools
tags: 
    - web
    - note
    - site
    - guide
banner_img: /img/bllm.png
---
# 开始MkDocs
## 安装和开始一个新项目
下述代码依次执行以下操作
- pip安装mkdocs包
- 新建项目并进入my-project
- 本地8000端口开一个网站用于调试预览

现在你可以打开`http://127.0.0.1:8000/`，你将看到默认的主页
```bash
pip install mkdocs
mkdocs new my-project
cd my-project
mkdocs serve
```
文件结构
```
my-project/
    docs/
        index.md
    mkdocs.yml
```

## 添加新页面
在docs下添加md文件并在mkdocs.yml添加导航  
```bash
curl 'https://jaspervdj.be/lorem-markdownum/markdown.txt' > docs/about.md
```
```yml
site_name: MkLorum
site_url: https://example.com/
nav:
    - Home: index.md
    - About: about.md
```

## 构建网站和部署到GitHub
在mkdocs.yml所在目录初始化git，提交并推送到你的远程仓库  
下面命令构建并推送site/目录到远程的gh-deploy分支，稍等片刻便可以看到你的网页部署成功
```bash
mkdocs build
mkdocs gh-deploy
```