# AI4C 文献库 · AI × Chemistry Literature (2022–2026)

---

## 1. 仓库结构

**仓库希望长成这样**：

```text
.
├── README.md                       ← 本文件
├── JACS/                           ← 一本刊一个文件夹
│   ├── README.md                   ← 该刊文献表
│   └── papers/                     ← 论文 PDF 原件
│       ├── 001-paper1.pdf
│       └── 002-paper2.pdf
├── Angew/
│   ├── README.md
│   └── papers/
├── NeurIPS/
│   ├── README.md
│   └── papers/
└── ...
```

## 2. 本次交付物

### 小组分工

| 小组 | 负责人（每组两人） | 负责会议 / 期刊 | 提交分支 |
| --- | --- | --- | --- |
| 第 1 组 | 林正立、刘弘毅 | `ICLR`；`KDD`；`Nature`；`Nature Methods` | `group1` |
| 第 2 组 | 高宇豪、朱晓楠 | `ICML`；`Nature Catalysis`；`Nature Chemical Biology`；`Cell Systems` | `group2` |
| 第 3 组 | 游文韬、吴龙涛 | `IJCAI`；`CoRL`；`RECOMB`；`ISMB` | `group3` |
| 第 4 组 | 廖晨希、蔡瑞翔 | `Nature Chemistry`；`Chem`；`ACS Central Science`；`Nature Synthesis` | `group4` |
| 第 5 组 | 陈思铭、黄传鑫 | `Nature Material`；`NeurIPS`；`Science`；`Nature Machine Intelligence` | `group5` |
| 第 6 组 | 刘锋、陈静 | `Nature Communication`；`Nature Genetics`；`Nature Medicine`；`Nature Biomedical Engineering` | `group6` |
| 第 7 组 | 江鑫、王凌睿 | `AAAI`；`Nature Computational Science`；`Nature Biotechnology`；`Bioinformatics` | `group7` |
| 第 8 组 | 张锦泓、林烨 | `MICCAI`；`IEEE TNNLS`；`TPAMI`；`Cell` | `group8` |
| 第 9 组 | 陆奔恺、张宇晨 | `JACS`；`Angew` | `group9` |
| 第 10 组 | 陈梓衡、施博文 | `Chemical Science`；`Advanced Materials`；`npj Computational Materials` | `group10` |


### 交付要求

每组把分管的 4 本刊物各做成一个文件夹，每个文件夹里必须有这**两样东西**：

| 交付物 | 内容 | 要求 |
| --- | --- | --- |
| `README.md` | 该刊的文献表 | 一行一篇，7 列填齐，序号不重复 |
| `papers/` | 论文 PDF 原件 | 一篇一个 PDF，文件名 = `序号-论文名.pdf` |

**文献表与 PDF 必须一一对应**：表格里每一行都能在 `papers/` 找到同序号的 PDF；`papers/` 里每个 PDF 也都能在表格里找到对应的行。

---

## 3. 表格格式

每个刊物文件夹里的 `README.md` 有一张表，**7 列，顺序固定**：

| 列 | 说明 |
| --- | --- |
| **序号** | 3 位数字，`001` 起，一刊内唯一 |
| **文献名** | 原文标题照抄，不翻译、不加书名号、结尾不加句号 |
| **年份** | 4 位数字，≥ 2022（正式出版年，不带「年」字） |
| **DOI** | 小写裸 DOI，见下方 DOI 规则 |
| **刊物** | 本文件夹的缩写，如 `JACS`、`NeurIPS` |
| **类型** | 研究 / 综述 / 数据集 / 软件 / 展望（默认「研究」） |
| **收集人** | 收集这篇论文的同学姓名 |

**一行模板：**

```markdown
| 001 | Machine-Learned Interatomic Potentials for Aqueous Electrolytes | 2023 | 10.1021/jacs.3c01234 | JACS | 研究 | 刘峰 |
```

这一行对应的 PDF 放进 `JACS/papers/`，文件名是：

```text
001-Machine-Learned-Interatomic-Potentials-for-Aqueous-Electrolytes.pdf
```

### 序号与 PDF 命名

- 序号 **3 位数字**，从 `001` 起，**每本刊独立编号**，一刊之内不能重复。
- 文件名固定格式：**`序号-论文名.pdf`**，序号必须与表格第一列完全一致。
- 论文名部分：**空格换 `-`**，`/ \ : * ? " < > |` 换 `-`，大小写和其余字符照抄（见上方例子）。
- 一篇论文只放一个 PDF（正文）；有关键补充材料，就与正文合并成一个 PDF。
- 改完名回头核对一眼：文件名开头的 3 位数字 = 表格第一列。

### DOI 规则

DOI 是全库唯一的去重键，格式必须统一，否则查重会失效。

1. **只写裸 DOI**，去掉前缀：
   - ❌ `https://doi.org/10.1021/jacs.3c01234`
   - ❌ `doi:10.1021/...`
   - ✅ `10.1021/jacs.3c01234`
2. **全部小写**。
3. 去掉尾部标点（`.` `,` `;` `)`）和空格。
4. **不要写成 Markdown 链接** `[文字](链接)`，只填纯文本。
5. 会议论文（NeurIPS / ICML / ICLR 等）确实没有 DOI 时，填该篇论文的正式页面链接；不要填会议首页或论文列表页，DOI 列不许留空。
6. 核验：浏览器打开 `https://doi.org/<你的DOI>`，能跳到正确论文页才算对；填写正式链接的论文，也要确认链接能打开对应论文页。

---

## 4. 提交方式：Pull Request

每组使用一个以小组命名的分支，例如第 1 组使用 `group1`，第 2 组使用 `group2`。完整流程是：**查看分工 → 创建小组分支 → 上传交付物 → 提交 PR → 负责人审核并合并**。请勿直接向主分支上传或提交交付物。

### 第一步：创建小组分支

1. 打开仓库，切换到主分支（通常为 `main`，以仓库实际设置为准）。
2. 点击文件列表上方的分支选择框，输入本组分支名，例如 `group1`，选择创建分支。
3. 确认当前分支显示为本组分支后，再开始上传。同组成员共用该分支；如果分支已经存在，直接切换到该分支，不要重复创建。

### 第二步：在小组分支上传交付物

1. 按分工表整理本组负责的 4 本刊物，目录结构遵循第 1 节：每本刊物一个文件夹，内含 `README.md` 和 `papers/`。
2. 在本组分支页面选择 **Add file → Upload files**，上传整理好的刊物文件夹，保留完整目录结构。刊物文件夹应直接位于仓库根目录，不要再套一层 `group1/` 等小组文件夹。
3. 填写提交说明，例如 `group1：上传 4 本刊物的文献表和 PDF`，将本次上传提交到 **本组分支**。
4. 上传后打开各刊物目录，确认文献表与 PDF 均已上传，文件名和序号对应，PDF 能正常打开。

### 第三步：提交 Pull Request

1. 在仓库页面点击 **Compare & pull request**；也可以进入 **Pull requests → New pull request**。
2. 将目标分支（**base**）设为主分支，将来源分支（**compare**）设为本组分支，例如 `group1`。
3. 检查改动列表，确认包含本组全部交付物，再填写 PR 标题和说明。
4. 点击 **Create pull request**，提交给负责人审核。**上传文件到分支后，还需要完成这一步，才算提交审核。**

**PR 标题示例：**

```text
group1：提交 JACS、Angew、刊物3、刊物4 文献及 PDF
```
