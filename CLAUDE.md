# Spirits · 灵境卜卦

## 项目概述
- **类型**：纯静态 HTML 单文件网站
- **功能**：易经卜卦（3铜钱摇卦法）
- **地址**：https://2559353251.github.io/spirits/
- **仓库**：https://github.com/2559353251/spirits

## 文件结构
```
Spirits/
├── index.html    ← 唯一核心文件（内嵌 CSS + JS）
├── README.md     ← 发布说明
└── CLAUDE.md     ← 本文件（AI 上下文）
```

## 技术架构
- 无依赖，纯 HTML + CSS + 原生 JS
- 左右双栏布局（左操作、右卦象），800px 断点响应式
- Canvas 粒子背景动画
- localStorage 持久化历史（最多 20 条）
- CSS 伪元素绘制铜钱（方孔 + 字面）
- requestAnimationFrame 物理动画（抛起→飘浮→下落→弹跳）
- GitHub Pages 部署，main 分支自动发布

## 核心功能模块

### 1. 摇卦流程（startDivination）
- 6 次摇爻，从下往上排
- 每次走龟壳仪式动画（tossCoins）：
  1. 铜钱隐入 → 龟壳浮现
  2. 龟壳剧烈摇晃（shellShake 关键帧）
  3. 龟壳开启消散 → 铜钱从壳心爆出
  4. 铜钱物理飞散到随机位置

### 2. 铜钱逻辑
- `randomPositions()` — 生成3个不重叠随机坐标（响应式尺寸）
- `animateCoinToss()` — 单枚钱币四段物理动画
- `getCoinPositions()` — 读取当前渲染位置
- coinIdle 呼吸动画（暂停于 .animating 类）

### 3. 卦象数据
- `buildHexagrams()` — 64卦完整数据库
- 键值：6位二进制字符串 '111111'~'000000'
- 每卦含 name、judgment（判词）、detail（解读）
- 变爻（6/9）→ 阴变阳/阳变阴 → 变卦

### 4. 界面元素
- `#turtleShell` — 龟壳 CSS 绘制（渐变 + 三重交叉线网格 + 遮罩）
- `.coin` — 铜钱，伪元素 ::before（方孔）::after（字）
- `.hex-line` — 卦爻线，.changing 变爻高亮橙色
- `.interpretation` — 右侧判词+解读

### 5. 快捷键
- 空格键 → 起卦（防连按锁）

## 发布命令
```bash
git add . && git commit -m "说明" && git push
```
