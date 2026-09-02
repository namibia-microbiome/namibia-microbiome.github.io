# Namibia–UK Biofertiliser Knowledge Exchange website

这是一个可直接用于 GitHub Pages 的 Jekyll 网站，结构仿照 ARUA
Microbiome Workshop 2025，使用同一类 Minimal Mistakes 主题和多页面导航。

## 本地预览

项目建议使用 Ruby 3.2 或更新版本：

```bash
bundle install
bundle exec jekyll serve --livereload
```

然后访问 `http://127.0.0.1:4000/`。

## GitHub Pages 部署

目标网址为 `https://namibia-microbiome.github.io/`。GitHub 用户或组织必须
命名为 `namibia-microbiome`，公开仓库必须命名为
`namibia-microbiome.github.io`。

在 GitHub 创建空仓库后，在本目录运行：

```bash
git remote add origin https://github.com/namibia-microbiome/namibia-microbiome.github.io.git
git push -u origin main
```

随后进入仓库的 **Settings → Pages**，在 **Build and deployment** 中选择
**Deploy from a branch**，并选择 **main** 和 **/(root)**。以后推送到 main
分支时，GitHub Pages 会自动重新构建网站。

## 发布到 GitHub Pages

目标网址为 `https://namibia-microbiome.github.io/`。GitHub 用户或组织名
必须是 `namibia-microbiome`，仓库名必须是
`namibia-microbiome.github.io`。

创建空仓库后，在本目录运行：

```bash
git init -b main
git add .
git commit -m "Initial website"
git remote add origin https://github.com/namibia-microbiome/namibia-microbiome.github.io.git
git push -u origin main
```

随后在 GitHub 仓库的 **Settings → Pages** 中，将 Source 设为
**Deploy from a branch**，选择 **main** 和 **/(root)**，然后保存。

## 页面

- 首页：简短项目介绍、三个核心主题和支持项目
- About：活动目的、合作框架和长期愿景
- Travel information：日期、地点、机场与签证入口
- Programme：2026 年 10 月 26–30 日按天概览
- People：组织者及合作机构
- Materials：后续培训资料入口

## 发布前需要补充

1. 温得和克的具体会场、住宿和接送信息
2. 报名表、资格和截止日期
3. 确认后的利益相关方和每日具体时间
4. 签证邀请信流程和紧急联系方式
5. 真实项目照片、机构 Logo 及获准使用的品牌规范（当前自然风景图为开放许可网络图片）
6. 培训资料、软件安装说明和开放协议下载链接
7. `_config.yml` 中的 `url`、`repository`（当前为本地占位值）与最终 GitHub Pages 地址

原始申请材料保留在 `Africa Seed Fund/` 和 `Africa Seed Fund2/`，并已在
`_config.yml` 中排除，不会被 Jekyll 复制到公开网站。
