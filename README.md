# 基于Jekyll的网站

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

## 使用 act 本地调试 GitHub Workflows 脚本

[act](https://github.com/nektos/act) 是一个可以在本地运行 GitHub Actions 工作流的工具，方便在推送到远程仓库前进行调试。

### 安装 act

可以通过 Homebrew 安装（推荐 macOS 用户）：

```
brew install act
```

或通过二进制包安装，详见 [act 官方文档](https://github.com/nektos/act#installation)。

### 本地运行 Workflows

在项目根目录下运行如下命令即可本地执行 `.github/workflows` 下的脚本：

```
act
```

你也可以指定事件类型，例如：

```
act push
```

### 解决容器内部网络问题（强烈推荐）

由于 act 运行时会在 Docker 容器内访问 GitHub，容器内部必须能正常连接外网。如果你本地使用了代理（如 Clash、V2Ray、ShadowSocks 等），需要将代理环境变量传递给容器，否则会出现 TLS handshake timeout 等网络错误。

推荐使用如下命令运行 act（适配 Apple M 系列芯片，并传递代理环境变量）：

```
act -W .github/workflows/update-changelog-version-release.yml --container-architecture linux/amd64 -s https_proxy=http://127.0.0.1:7890 -s http_proxy=http://127.0.0.1:7890 -s all_proxy=socks5://127.0.0.1:7890
```

- 其中 7890 为你的本地代理端口，请根据实际情况修改。
- 该命令会将代理环境变量传递到容器内，确保容器内能正常访问 GitHub。

### 注意事项
- 需要确保本地有 Docker 环境，act 依赖 Docker 运行。
- 某些 Actions 可能依赖于 GitHub 上的环境或密钥，需提前配置好本地 secrets。

更多用法请参考 [act 官方文档](https://github.com/nektos/act)。
