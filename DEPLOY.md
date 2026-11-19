# 部署到 GitHub Pages

部署包是自包含的：`index.html` + `phaser.min.js`（已本地化，不依赖外网 CDN）。

## 1. GitHub 建一个空仓库

- 名字随意，例如 `card-battler`
- 选 **Public**（免费版 Pages 只支持公开仓库）
- **不要**勾 Add README / .gitignore / license —— 保持空仓库

## 2. 把本地仓库推上去

在本目录执行（把 `<用户名>` 换成你的 GitHub 用户名）：

```bash
git remote add origin https://github.com/<用户名>/card-battler.git
git push -u origin main
```

首次 push 会弹 GitHub 登录窗口，登录一次就行；弹不出来的话用 Personal Access Token 当密码。

## 3. 开 Pages

仓库页 → Settings → Pages

- Source: **Deploy from a branch**
- Branch: **main** / folder: **/ (root)**
- Save

等 1~2 分钟，访问：

```
https://<用户名>.github.io/card-battler/
```

## 4. 发给朋友

直接发上面这个链接。微信里打开就是竖屏，点牌可玩。

## 更新游戏

改完 `index.html` 后：

```bash
git add -A
git commit -m "update"
git push
```

Pages 会自动重建，几十秒生效。

## 注意

- 国内访问 `github.io` 时快时慢，朋友打不开的话换 Cloudflare Pages（同样免费、可连私有仓库）。
- 别把 `.git` 目录发给别人；要发文件就发 zip。
