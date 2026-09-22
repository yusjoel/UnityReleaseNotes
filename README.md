# UnityReleaseNotes

Unity 的发布日志归档，共 **1601 个版本**，可以通过 [索引页](https://yusjoel.github.io/UnityReleaseNotes/) 访问。

## 内容

| 内容 | 说明 |
|---|---|
| `<版本>.md` | 发布日志，来自 Unity 官方导出的 Markdown |
| `<版本>.downloads.json` | 该版本的下载清单（编辑器安装包 / 模块 / 语言包，以及 Unity Hub 深链） |
| `index.html` | 索引，按大版本分组，每组是一张「小版本 × f/p/b/a」矩阵 |
| `index-<大版本>.html` | 该大版本的完整版本列表 |
| `download.html?f=<路径>` | 下载页，读取对应的 `.downloads.json` 并渲染成可点的链接 |
| `Backup/` | 迁移前的原始 HTML，仅作存档，不再维护 |

目录按版本号第一段划分：`3/ 4/ 5/ 2017/ … 2023/ 6000/`。
其中 `6000/` 对应 Unity 6 的版本号，覆盖 2024 年以后的发布。

## 历史

原始库来自 UnityCommunity 的 [UnityReleaseNotes](https://github.com/UnityCommunity/UnityReleaseNotes)，
因为长时间不更新，所以自己 fork 了一个库，但又发现 fork 的库无法使用搜索功能所以自己重新建了一个库。

## 为什么要建这个库

* 访问不了 www.unity3d.com 的朋友，可以通过这个库下载各个版本的 Unity，查看发布日志
* 可以使用 Github 的搜索功能，来查看某个问题在哪些版本有修正，在某个方面后续版本有些什么优化等等

## 数据来源

* 发布日志：[services.unity.com](https://services.unity.com/api/live-platform/v1/graphql) 的 `getUnityReleases` 查询
  （必须带 `entitlements: [XLTS]`，否则会漏掉 29 个长期支持补丁版）
* 下载清单：Unity Hub 的 [公开接口](https://services.api.unity.com/unity/editor/release/v1/releases)；
  该接口查不到的 XLTS 版本从 [What's new in Unity](https://unity.com/releases/editor/whats-new/) 页面补齐

> 两个接口都是未公开的内部接口，没有稳定性承诺。归档工具会拿 [sitemap](https://unity.com/sitemap.xml)
> 做交叉校验 —— 两边版本集合一旦不一致就说明枚举坏了。

## 说明

* **3.x / 4.x 以及 5.0–5.3 的 49 个版本是孤本。** Unity 官网已经下架，接口也查不到
  （接口最老只到 5.0.0f4），这些内容是从早期归档的 HTML 转换而来，原始 HTML 保留在 `Backup/` 下。
* **6 个 Unity 5.1 版本没有下载清单**（`5.1.0b3`–`b6`、`5.1.0f1`–`f2`）。Unity 从未为它们发布过
  直接安装包（实测编辑器 URL 全部 404），页面上只有 Download Assistant。这些版本仍保留了版本号和 Hub 深链。

## 其他推荐

* [Unity ReleaseNote](https://smartphone-games.net/UnityReleaseNote/)
  * 可以按模块查看Release Note
* [Unity历史版本下载列表](http://1vr.cn/?p=568)
  * 提供下载链接，比较全，更新也频繁
* [Unity I Tell You](https://unityitellyou.github.io/)
  * 提供直接下载
