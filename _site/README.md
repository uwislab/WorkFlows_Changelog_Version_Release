# 我的Jekyll网站

这是一个使用Jekyll构建的简单美观的网站。

## 功能特点

- 简洁的首页布局
- 响应式设计
- 博客文章支持
- 关于页面
- 基本的导航菜单

## 安装说明

1. 确保已安装Ruby和RubyGems
2. 安装Jekyll和Bundler:
   ```
   gem install jekyll bundler
   ```
3. 克隆此仓库
4. 进入项目目录
5. 安装依赖:
   ```
   bundle install
   ```

## 运行网站

在项目目录中运行以下命令:

```
 bundle exec jekyll serve
```

然后在浏览器中访问 `http://localhost:4000` 查看网站。

## 部署到GitHub Pages

1. 创建一个GitHub仓库
2. 将代码推送到仓库
3. 在仓库设置中，将GitHub Pages的源设置为`main`分支
4. 等待几分钟，网站将在 `https://<username>.github.io/<repository-name>/` 上可用。
