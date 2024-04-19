---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: /images/background.jpg
# some information about your slides, markdown enabled
title: Welcome to Slidev
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# apply any unocss classes to the current slide
class: text-center
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# https://sli.dev/guide/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/guide/syntax#mdc-syntax
mdc: true
lineNumbers: true
---

# GitHub Codeapacesによる<br>ポータビリティ性の高い<br>環境構築とスムーズな<br>チーム開発

2024-04-20@VS Code Conference Japan 2024

Yuhei FUJITA

---

# ふじた。ひらがなみっつでふじた。<br>よぶときはふじたさん。

<div class="grid grid-cols-4 gap-4">

<div>


![icon](https://github.com/YuheiFUJITA.png)

</div>
<div class="col-span-3">

- 名前: Yuhei FUJITA（<ruby>藤<rt>ふじ</rt></ruby><ruby>田<rt>た</rt></ruby> <ruby>悠<rt>ゆう</rt></ruby><ruby>平<rt>へい</rt></ruby>）
- X(Twitter): [@Yuhei_FUJITA](https://twitter.com/Yuhei_FUJITA)
- GitHub: [@YuheiFUJITA](https://github.com/YuheiFUJITA)
- コミュニティ運営: [Vue Fes Japan](https://vuefes.jp/) / [VS Code Meetup](https://vscode.connpass.com/) / [ChatGPT Community(JP)](https://chatgpt.connpass.com/) / [フロントエンドカンファレンス北海道2024](https://fortee.jp/frontend-conf-hokkaido-2024)
- 趣味: [自然淘汰キャンプ](https://x.com/Yuhei_FUJITA/status/1748854045664829587) / [フィルムカメラ](https://www.instagram.com/yuhei_fujita.film/) / [SIGMA fp L買うよう背中を<ruby>押された<rt>どつかれた</rt></ruby>](https://twitter.com/Yuhei_FUJITA/status/1780934056479494332)

</div>
</div>

---
layout: statement
---

# What's GitHub Codespaces ?

---

# GitHubが用意したリモート環境で実行されるVS Code

![](/images/open-on-browser.png)

<v-click><Arrow color="red" x1="300" y1="180" x2="150" y2="110" width="4" /></v-click>
<v-click><Arrow color="red" x1="700" y1="200" x2="800" y2="120" width="4" /></v-click>

---

# /^リモート環境(だから|でも)できること$/

<div class="grid grid-cols-2 gap-4">

<div>

## リモート環境<span v-mark="{ at: 0, color: 'red', type: 'underline' }">だから</span>できること

- <span v-mark="{ at: 1, color: 'red', type: 'circle' }">ブラウザ</span>からアクセス可能
- <span v-mark="{ at: 2, color: 'red', type: 'circle' }">低スペックPC</span>でも利用可能
- <span v-mark="{ at: 3, color: 'red', type: 'circle' }">環境構築</span>が不要
- なんなら<span v-mark="{ at: 4, color: 'red', type: 'circle' }">タブレット</span>でも利用可能


</div>
<div>

## リモート環境<span v-mark="{ at: 0, color: 'red', type: 'underline' }">でも</span>できること

- <span v-mark="{ at: 5, color: 'red', type: 'circle' }">拡張機能</span>がそのまま使える
- <span v-mark="{ at: 6, color: 'red', type: 'circle' }">Terminal</span>も使える
- <span v-mark="{ at: 7, color: 'red', type: 'circle' }">docker</span>も使える

</div>
</div>

---
layout: fact
---

# github.devと<br>何が違うの?

※github.dev = 任意のrepositoryで <kbd>.</kbd> 押すと開くやつ

---

# github.devはあくまでViewer

![](/images/github.dev.png)

<v-click><Arrow color="red" x1="350" y1="210" x2="230" y2="210" width="4" /></v-click>
<v-click><Arrow color="red" x1="500" y1="400" x2="400" y2="400" width="4" /></v-click>

---

# github.dev vs GitHub Codespaces

| 機能 | github.dev | GitHub Codespaces |
| :-: | :-: | :-: |
| ブラウザから利用 | ○ | ○ |
| ローカルから利用 | ✗ | ○ |
| 拡張機能 | <span v-mark="{ at: 1, color: 'red', type: 'underline' }">△（プロセスが実行される系はNG）</span> | ○ |
| Terminal | ✗ | ○ |
| docker | ✗ | ○ |
| 料金 | <span v-mark="{ at: 2, color: 'red', type: 'circle' }">無料</span> | <span v-mark="{ at: 2, color: 'red', type: 'circle' }">有料（無料枠あり）</span> |

---
layout: center
---

[![GitHub Codespaces overview - GitHub Docs](/images/codespaces-diagram.png)](https://docs.github.com/en/codespaces/overview)

---
layout: statement
---

# 料金

---

# GitHub Codespacesの無料枠

毎月この範囲であれば無料

| アカウントプラン | 1か月あたりの<br>ストレージ | 1か月あたりの<br>コア時間 |
| --- | --- | --- |
| 個人用アカウント用の GitHub | 15 GB/月 | 120 |
| GitHub Pro | 20 GB/月 | 180 |

- 無料枠内でも支払い方法の登録が必要（クレジットカード or PayPal）
- <span v-mark="{ at: 1, color: 'red', type: 'underline' }">Organizationには無料枠なし</span>（Organizationで許可する必要あり）
- Organizationと個人が両方課金設定している場合はOrganizationの支払い

---

# 料金

| コンポーネント | マシンの種類 | Unit of measure | 含まれる<br>使用量の乗数 | Price |
| --- | --- | --- | --- | --- |
| コンピューティング | 2 コア | 1 時間 | 2 | $0.18 |
| コンピューティング | 4 コア | 1 時間 | 4 | $0.36 |
| コンピューティング | 8 コア | 1 時間 | 8 | $0.72 |
| コンピューティング | 16 コア | 1 時間 | 16 | $1.44 |
| コンピューティング | 32 コア | 1 時間 | 32 | $2.88 |
| ストレージ | ストレージ | 1GB-月 | 適用なし | $0.07 |

---
layout: statement
---

# How to use

---

# ブラウザから起動する

repositoryの `Code` から起動できる

![ブラウザ上から起動する](/images/open-from-web.png)

---

# 起動ボタンから起動する

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/user/repo)

````md magic-move
```text
https://codespaces.new/user/repo
```
```html
<a href='https://codespaces.new/user/repo'>
  <img src='https://github.com/codespaces/badge.svg' alt='Open in GitHub Codespaces' style='max-width: 100%;' >
</a>
```
```markdown
[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/user/repo)
```
````

![](/images/codespaces-button.png)

---

# ローカルから起動する

VS Codeの拡張機能から起動できる

![](/images/open-on-desktop.gif)

---
layout: statement
---

# チーム開発での活用

---

# OS・マシンスペックの差を気にせずに開発

![](/images/conf-2022-2023.png)

---

# Dev Containerの設定をしておけばそのまま使える

.devcontainer/devcontainer.json

````md magic-move
```json
{
	"name": "Slidev",
	"dockerComposeFile": [
		"../docker-compose.yml",
		"docker-compose.yml"
	],
	"service": "local",
	"workspaceFolder": "/workspaces/${localWorkspaceFolderBasename}"
}
```
```json
{
	"name": "Slidev",
	"dockerComposeFile": [
		"../docker-compose.yml",
		"docker-compose.yml"
	],
	"service": "local",
	"workspaceFolder": "/workspaces/${localWorkspaceFolderBasename}",
	"customizations": {
		"vscode": {
			"extensions": [
				"Vue.volar",
				"antfu.slidev",
				"yzhang.markdown-all-in-one",
				"streetsidesoftware.code-spell-checker",
			]
		}
	}
}
```
```json
{
	"name": "Slidev",
	"dockerComposeFile": [
		"../docker-compose.yml",
		"docker-compose.yml"
	],
	"service": "local",
	"workspaceFolder": "/workspaces/${localWorkspaceFolderBasename}",
	"customizations": {
		"vscode": {
			"extensions": [
				"Vue.volar",
				"antfu.slidev",
				"yzhang.markdown-all-in-one",
				"streetsidesoftware.code-spell-checker",
				"GitHub.copilot",
				"GitHub.copilot-chat"
			],
			"settings": {
				"editor.fontSize": 14,
				"editor.tabSize": 2,
				"editor.insertSpaces": false,
				"editor.indentSize": 2,
			}
		}
	}
}
```
````

---

# Pull RequestのレビューをCodespaces上で行う

ローカルでcheckoutせずにレビューが可能

![](/images/open-from-pr.png)
<Arrow color="red" x1="800" y1="380" x2="765" y2="285" width="4" />

---

# 急な対応が必要な場合にも対応可能

---

# 引用

- [GitHub Codespaces overview \- GitHub Docs](https://docs.github.com/en/codespaces/overview)
- [About billing for GitHub Codespaces \- GitHub Docs](https://docs.github.com/en/billing/managing-billing-for-github-codespaces/about-billing-for-github-codespaces)
