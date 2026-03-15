# CASA0023 Group Presentation
**Remotely Sensing Cities and Environments · UCL 2026**

🌐 **Live Presentation:** `https://arthurzhang69.github.io/CASA0023-GROUP-PRESENTATION/`

---

## 📁 Repo Structure

```
CASA0023-GROUP-PRESENTATION/
│
├── index.Rmd          ← ⭐ 最终演示文稿主文件（Arthur维护）
├── index.html         ← Knit 后生成，GitHub Pages 渲染这个
├── custom.css         ← 共享主题样式（根目录css的除了Arthur之外其他人不要修改⚠,
                         然后自己文件夹里的css可以定时跟根目录里的css同步一下）
├── .gitignore         ← GitHub大文件忽略，切勿往GitHub上传大文件(>100MB)堵塞tree
├── README.md
│
├── Content From HaoYu Jiang/
├── Content From JianShu Wu/
├── Content From Li Sheng/
├── Content From ShiYao Zhang/
└── Content From ZheXiang Zhou/
```

---

## ✍️ 每个人的文件夹怎么用

### Step 1 · 确认文件已就位

每个人的文件夹里已经放好了：

```
Content From [Your Name]/
├── preview.Rmd    ✅ 已放好，包含你负责的 slides 内容
└── custom.css     ✅ 已放好，共享主题样式
```

无需任何操作，直接从 Step 2 开始。

### Step 2 · 在 preview.Rmd 里写你的 slides

打开 `preview.Rmd`，在文件末尾按格式添加你负责的 slides：

```rmd
---

## Your Slide Title

.slide-label[Slide XX · Your Name]

内容写在这里...

.footnote[参考文献]
```

每张 slide 之间用 `---` 分隔。

### Step 3 · 本地预览

在 RStudio 里打开 `preview.Rmd`，点击 **Knit**，浏览器会自动弹出预览。

样式与最终版完全一致，所见即所得。

### Step 4 · 把图片也放在自己文件夹里

```
Content From [Your Name]/
├── preview.Rmd
├── custom.css
├── fig_01_map.png       ← 图片放这里
└── fig_02_chart.png
```

引用图片时：

```r
knitr::include_graphics("Content From [Your Name]/fig_01_map.png")
```

> ⚠️ 路径从 **repo 根目录** 出发写，不要用 `./`

### Step 5 · 推送到 GitHub

```bash
# 每次开始前先同步
git pull

# 编辑完成后
git add "Content From [Your Name]/"
git commit -m "简短描述，比如：Add slide 3 vulnerability diagram"
git push
```

**只 add 自己的文件夹**，不要碰其他人的文件夹和根目录文件。

---

## 🔀 最终整合流程（Arthur操作）

当所有人完成各自内容后，Arthur按以下步骤合并：

### Step 1 · 确认每个人的 preview.Rmd 能正常 Knit

逐一打开每个人文件夹里的 `preview.Rmd` 点 Knit，确保没有报错。

### Step 2 · 在 index.Rmd 里按顺序引入每个人的内容

### Step 3 · Knit index.Rmd 生成最终文件

RStudio 中打开根目录的 `index.Rmd`，点击 **Knit**，生成 `index.html`。

如果报错，通常是某人的图片路径写错了，逐一检查 `include_graphics()` 的路径。

### Step 4 · 推送，GitHub Pages 自动更新

```bash
git add index.html libs/
git commit -m "Final presentation build"
git push
```

几分钟后访问页面顶部的链接即可看到在线版本。

---

## ⚠️ 常见问题

| 问题 | 原因 | 解决方法 |
|------|------|---------|
| Knit 报错找不到图片 | 路径用了 `./` 或相对路径 | 改成从根目录出发的完整路径 |
| 样式不对 | `custom.css` 没放在同级目录 | 确认文件夹里有 `custom.css` |
| Push 被拒绝 | 忘记先 pull | 先 `git pull` 再 push |
| 图片太大推不上去 | 文件超过 100MB | 大文件放 Google Drive，repo 里只放导出的图表截图 |

---

*Built with [Xaringan](https://github.com/yihui/xaringan) · R · ggplot2 · All EO data via Google Earth Engine*
