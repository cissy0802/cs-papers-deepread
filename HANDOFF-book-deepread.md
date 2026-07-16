# HANDOFF — 上线 book-deepread（书籍精读 routine，首本 DDIA）

给**能访问所有仓库**的新 session 用。上一个 session 已把整套脚手架写好、跑通自检、推到分支；
但因权限受限无法建新仓 / 无法读 system-design，剩下的「建仓 + 迁移 + Pages + 版式对齐」交给你。

---

## 1. 背景 / 目标

BigCat 已有姊妹站 **`cissy0802/cs-papers-deepread`**（IT 论文精读，云端 routine 逐篇写论文精读页）。
现要并列一个 **书籍精读 routine**：通用「计算机好书逐章精读」，**首本 = DDIA**（Designing
Data-Intensive Applications, Kleppmann 2017）全 12 章，一章一页、中英双语、科普/精读双模式。
最终形态 = 一个新独立仓 **`cissy0802/book-deepread`** + GitHub Pages（`cissy0802.github.io/book-deepread`）
+ 一个 cron routine（cron 由 BigCat 自己设）。

## 2. 当前状态（已完成，别重做）

整套脚手架 + 样例第 1 章（中英）已写好、**自检全过**、已 commit + push：

- **位置**：仓库 `cissy0802/cs-papers-deepread`，分支 **`claude/book-deep-read-routine-brh6ga`**，
  目录 **`book-deepread/`**，提交 `dbbf365`。
- **这个目录就是新仓的根布局**，10 个文件：

| 文件 | 说明 |
|---|---|
| `CLAUDE.md` | routine 执行说明（论文精读规格适配成书籍逐章精读：0选题→1写页八节→2写作硬规则→3发布→4通知→index roadmap 维护） |
| `TOPICS.md` | 书籍/章节清单，首本 DDIA 全 12 章（按 Part 排开，每章带 slug `ddia-chNN-...`）。routine 只读不改 |
| `index.html` / `index.en.html` | roadmap-first 书架，12 章按 Part 分组灰色占位，Ch1 已原地转成链接 |
| `ddia-ch01-reliable-scalable-maintainable-book1.html` / `.en.html` | 样例第 1 章（锁模板），八节 + 科普版 + 3 张内联 SVG |
| `publish.sh` | 共享发布脚本，**与 cs-papers-deepread 完全一致，零改动**（已支持 `book` kind） |
| `.github/workflows/inject-comments.yml` | 共享脚本自动注入工作流，**零改动** |
| `README.md` / `.gitignore` | 站点描述 / `.DS_Store` |

**自检已通过**：`<div>` 平衡（各文件 open==close）；内容页**未**硬写四个共享脚本
（comments/search/index-button/i18n-tts，由 Action 注入）；index 引用到样例文件；
英文页除 langbar「中文 →」外无汉字；`localStorage` key = **`bookread-mode`**（与论文站
`cspapers-mode` 区分，同源 `cissy0802.github.io` 下不冲突）；中文样例 3443 CJK 字（目标 3000–4500）。

## 3. 你要做的事

### A. 建仓 + 迁移（必做）
1. 建**空 public 仓** `cissy0802/book-deepread`（description 建议：`书籍精读 — 计算机好书逐章精读、提纯（首本 DDIA）`）。
2. 把上面分支里 `book-deepread/` 的**全部内容（含 `.github/`、`.gitignore`）搬到新仓根目录**并推到 `main`。
   拿到源文件的两种方式任选：
   - 从分支取：`git fetch origin claude/book-deep-read-routine-brh6ga` 后 `git checkout FETCH_HEAD -- book-deepread`，
     再把 `book-deepread/` 内容复制到新仓工作区根目录；
   - 或直接从 GitHub 读该分支下 `book-deepread/` 各文件内容，逐个写进新仓。
   参考命令：
   ```bash
   # 在 cs-papers-deepread 的该分支工作区里：
   mkdir -p /tmp/book-deepread && cp -r book-deepread/. /tmp/book-deepread/
   cd /tmp/book-deepread && git init -b main && git add -A
   git -c user.name=BigCat -c user.email=chengchen0802@gmail.com commit -m "init book-deepread: 书籍精读 routine + DDIA Ch1 样例"
   git remote add origin https://github.com/cissy0802/book-deepread.git
   git push -u origin main
   ```
   （push 后 `inject-comments.yml` 会自动跑一次，给页面注入四个共享脚本并 bot commit——预期行为。）
3. 新仓 **Settings → Pages**：source 选 `main` / 根目录，启用。等生效后访问验证：
   - `https://cissy0802.github.io/book-deepread/`（书架，Ch1 可点、Ch2–12 灰占位）
   - `https://cissy0802.github.io/book-deepread/ddia-ch01-reliable-scalable-maintainable-book1.html`

### B. 版式对齐 system-design（上个 session 没做成的）
上个 session 无法把 `cissy0802/system-design` 加进 scope（add_repo 审批门没过），
所以样例是照 cs-papers 的 `paper1`（本身已「向 system-design 看齐」）做的。你能访问全部仓，
请：clone / 读 `cissy0802/system-design` 的 index 与内容页，核对书籍站的版式语言
（渐变标题、mono 小标签/元信息、玻璃拟态卡片、间距/圆角/卡片层次）。**若 system-design 有更精致处，
以它为准微调** `book-deepread` 的内联 `<style>`（两个 index + 样例章的 zh/en 四处保持一致）。
注意：**只调版式骨架，别动本站专属的蓝→紫强调色**（`#5b9df9`→`#9b6cf5`，用于和琥珀色论文站区分）。

### C. cron（BigCat 自己设，你不用建，除非他另说）
routine 每次触发：读 `book-deepread/CLAUDE.md` → 从 `TOPICS.md` 顶部往下挑第一个没做的章
（`ls *-book*.html` 去 `-bookN` 比对 slug；下一篇是 Ch2 `ddia-ch02-data-models-query-languages`）→
按八节写 zh+en 两页 → index 原地把该章灰行转链接 → `./publish.sh` 推 main → PushNotification。
建议节奏每天/每两天一章。

## 4. 必须保持的设计不变量（改动时别破坏）

- **文件名**：`{slug}-book{N}.html` + `.en.html`，`N` = 写作顺序（现有最大 N+1，样例已占 N=1），与章号解耦。
- **配色**：蓝 `#5b9df9` → 紫 `#9b6cf5`，暗底 `#0f1216`，强调字 `#8fbaff`。别改回琥珀/青绿。
- **localStorage key = `bookread-mode`**（内容页页尾内联 IIFE 里）。
- **八节结构**（精读版）：一句话 / 坐标 / 这章要解决什么 / 核心内容讲透 / 关键权衡与选型 /
  为什么重要·落到真实系统 / 易错点与争议 / 要点；Glossary 作 §1 后的独立 `<h2>` 小节；外加科普版 `.mode-pop`。
- **内容页绝不硬写** comments.js/search.js/index-button.js/i18n-tts.js（Action 注入）；index 页可硬写（已硬写）。
- `publish.sh`、`inject-comments.yml` 与 cs-papers-deepread 保持一致，别改。
- `TOPICS.md` 人工维护、routine 只读（`publish.sh` 硬卡其改动）。

## 5. 上个 session 遇到的阻碍（说明为何没一步到位）

- `mcp__github__create_repository` → **403 Resource not accessible by integration**（GitHub App 无建仓权限）。
- `add_repo cissy0802/system-design` → 反复 **requires approval**，审批门未放行，读不到 system-design。
- 故走 fallback：脚手架暂存在 cs-papers-deepread 的 feature 分支 `book-deepread/` 目录，等你迁移。

## 6. 验证清单（迁移后逐项过）

- [ ] 新仓 `cissy0802/book-deepread` 存在，10 个文件在根目录（`.github/workflows/inject-comments.yml` 就位）。
- [ ] Pages 生效：书架页 + 样例章两个 URL 都能打开。
- [ ] 样例章：modebar 科普/精读切换正常、默认落科普版、刷新后 localStorage 记住选择；3 张 SVG 正常渲染；
      langbar 中英互跳；英文页无多余汉字。
- [ ] `git status` 干净；Action 注入四脚本的 bot commit 已出现在 main。
- [ ] （可选）版式已对齐 system-design；蓝→紫配色未被改动。
