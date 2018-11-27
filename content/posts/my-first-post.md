---
title: "NetlifyとHugoを使って静的サイトを構築するメモ"
date: 2018-11-27T00:03:27+09:00
draft: false
---

Hugoを使って、Netlifyで配信するまで。

### Setup Hugo
```
$ brew install hugo
$ hugo version
$ hugo new site isss802
$ cd isss802
```

### テンプレート設置
```
$ cd themes/
$ git clone git@github.com:Lednerb/bilberry-hugo-theme.git
$ cd bilberry-hugo-theme
$ rm -fr .git
$ cd ../../
```

### Config
```
$ vim config.toml
baseURL = "https://isss802.link"
languageCode = "ja-JP"
title = "isss802.link"
theme = "bilberry-hugo-theme"
```

### 記事作成
```
$ hugo new posts/my-first-post.md
$ vim content/posts/my-first-post.md

---
title: "NetlifyとHugoを使って静的サイトを構築するメモ"
date: 2018-11-27T00:03:27+09:00
draft: false
---

Hugoを使って、Netlifyで配信するまで。
```

### テスト
```
$ hugo server --buildDrafts
```
http:localhost:1313
にてアクセスして表示を確認

### Git
```
$ git init
$ git add -A
$ git commit -m "first commit"
$ git remote set-url origin git@github.com:isss802/isss802.link.git
$ git push origin master
```

### Netlify
アカウントを作成し、Githubのレポジトリに紐付ける。
必要に応じてカスタムドメインの設定をして、ホスティング完了。

[Netlify: All-in-one platform for automating modern web projects.](https://www.netlify.com/)
