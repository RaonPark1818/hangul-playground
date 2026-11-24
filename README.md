# 한글 놀이터 · 韩语小星星

给 5 岁孩子（乐乐）做的韩语启蒙小游戏。中文界面、零基础可玩、单文件离线运行。

![age](https://img.shields.io/badge/age-5%E5%B2%81-FFC94A) ![single file](https://img.shields.io/badge/single--file-HTML-4FCB9B) ![no deps](https://img.shields.io/badge/dependencies-none-54C3F0)

## 三个玩法

| 关卡 | 玩法 | 目的 |
|---|---|---|
| 字母乐园 | 14 个辅音 + 10 个元音，点一下听字母名和例词 | 建立字形和读音的第一印象 |
| 听音找一找 | 播放韩语单词，从 4 张图里选出对的（10 题一轮） | 听力辨别，不依赖认字 |
| 记忆翻翻卡 | 6 对图文卡片，翻开把图片和韩语单词配对 | 词形记忆 + 复述 |

每答对一次得一颗小星星，攒够 5/12/20/30 颗解锁徽章，进度保存在浏览器 localStorage。

## 怎么打开

直接双击 `index.html`，用 Chrome / Safari / Edge 打开即可，不需要安装、不需要联网（字体和语音是调用系统的）。

想放到线上，把仓库设为 Pages 即可（见下）。

## 发音说明

游戏用浏览器内置的 `speechSynthesis`，自动挑选设备的韩语语音（macOS/iOS 常见为 Yuna）。

- 有韩语语音：会自动朗读单词；没有的话不会用中文音色乱读，只提示安装语音包。
- macOS：系统设置 → 辅助功能 → 朗读内容 → 系统声音 → 管理声音，勾选「韩语」。
- 建议用 Safari 或 Chrome，iOS 上首次点击需要用户手势才会出声（正常现象）。

## 部署到 GitHub Pages

1. 打开仓库 Settings → Pages
2. Source 选 `Deploy from a branch`
3. Branch 选 `main`，目录选 `/ (root)`，Save
4. 等 1 分钟左右，访问 `https://raonpark1818.github.io/hangul-playground/`

仓库根目录的 `index.html` 就是入口，无需构建。

## 定制

- 换孩子名字：`index.html` 里搜「乐乐，一起玩韩语吧」。
- 加/改单词：脚本里的 `WORDS`（听音和翻牌共用）、`CONSONANTS`、`VOWELS` 三组数据。
- 配色：CSS 顶部 `:root` 变量。

## 设计取舍

- 全部按钮 ≥ 44px，适合幼儿手指。
- 答错不扣分、不打断，只抖动提示，允许继续选。
- 一轮 10 题 / 6 对，控制在 5–10 分钟内。
- 无外部依赖、无埋点、无账号，纯本地。
