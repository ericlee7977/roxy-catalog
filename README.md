# Roxy 产品查询（GitHub Pages + Siri）

用手机对 Siri 说产品名，Safari 打开产品卡：大图、SKU、规格、二维码。

## 1. 上传到 GitHub

1. 打开 https://github.com/new
2. Repository name 填：`roxy-catalog`
3. Public
4. 不要勾选 Add README（本地已有文件）
5. Create repository

在仓库页点 **Add file → Upload files**，把本文件夹里的文件全部上传：

- `index.html`（必须，网站首页）
- `.nojekyll`（让 GitHub 原样发布页面）
- `README.md`（可选）

点 **Commit changes**。

## 2. 打开 GitHub Pages

1. 仓库页：**Settings → Pages**
2. Branch 选 `main`（或 `master`），目录选 `/ (root)`
3. Save
4. 等 30–60 秒，刷新本页，会出现地址：

```
https://你的用户名.github.io/roxy-catalog/
```

电脑浏览器打开试：

```
https://你的用户名.github.io/roxy-catalog/?q=lemon
https://你的用户名.github.io/roxy-catalog/?q=116812A
https://你的用户名.github.io/roxy-catalog/?q=柠檬
```

能看到图和卡片，再绑 Siri。

## 3. iPhone 快捷指令

1. 打开「快捷指令」→ 新快捷指令，名称：`查产品`
2. 添加 **询问**，问题：`要查哪个产品？`
3. 添加 **URL**，内容为（换成你的用户名）：

```
https://你的用户名.github.io/roxy-catalog/?q=
```

然后把「询问结果」接到 `q=` 后面。

4. 添加 **打开 URL**
5. 右上角 ⓘ → **添加到 Siri**，短语：`查产品`

说：嘿 Siri，查产品 → lemon

## 4. 目录更新后

重新导出 Catalog Machine CSV，运行：

```bash
python3 convert_catalog.py catalogmachine.csv --out ./out
```

用新的页面覆盖仓库里的 `index.html`，再 Commit。Pages 一两分钟后自动更新。
