# 🪙 灵境卜卦 · Spirits I-Ching

> 在线地址：**[2559353251.github.io/spirits](https://2559353251.github.io/spirits/)**

---

## 修改 & 发布

在项目目录 `Spirits` 下打开终端，执行：

```bash
git add . && git commit -m "更新说明" && git push
```

推送后约 **1 分钟** 网站自动更新。

---

## 免输 Token（推荐）

让 Git 缓存你的凭证，不用每次输入 Token：

```bash
git config --global credential.helper cache
```

设置后首次 push 输入 Token，之后一段时间内自动记住。

---

## 目录结构

```
Spirits/
├── index.html    ← 网站主文件（单文件，内嵌 CSS + JS）
├── README.md     ← 本说明文件
└── .git/         ← Git 仓库（勿删）
```

## 技术说明

- 纯静态 HTML，无依赖，直接浏览器打开
- 64 卦完整数据库 + 判词解读
- 三铜钱摇卦法（6/7/8/9）
- 龟壳动画 + 铜钱物理散射
- Canvas 粒子背景
- localStorage 历史记录
