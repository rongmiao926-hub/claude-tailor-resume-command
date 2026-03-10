# Tailor Resume for Claude

这是一个给 Claude Code 用的自定义命令，文件位置是 `.claude/commands/tailor-resume.md`。

它的目标不是只帮你“修饰一份已有简历”，而是把整个定制简历流程串起来：先吸收你所有版本的简历，建立经历池；再批量读取一个或多个 JD；然后找出你经历和岗位要求之间的 gap，主动追问你可能遗漏的相关经历；最后按目标 JD 重写内容，并输出新的 Word 简历。

如果你之前为不同岗位改过很多版简历，这个命令尤其有价值，因为它能把那些散落在不同版本里的经历重新整合起来。

## 核心能力

### 1. 多版本简历 -> 经历池

你可以把所有版本的简历一起交给它。它会把不同版本里的经历、项目、技能、成果全部提取出来，合并成一个完整的经历池。以前某个版本里写过、后来删掉的内容，也能重新找回来。

### 2. 批量喂入 JD

你可以一次喂多个 JD。支持文本、文件、链接、截图；如果把多个岗位的截图放进同一个文件夹，它也会逐个读取、逐个分析。

### 3. 挖掘 gap 经历

它会对比你的经历和 JD 要求，找出 gap，然后主动发问。很多时候你不是没有相关经验，而是没有意识到某段经历可以为这个岗位服务。它会帮你把这些经历挖出来。

### 4. 针对 JD 润色改写

它会根据这个具体岗位来改写你的经历，按 STAR 原则重组信息。不是泛泛地替换词，而是真正调整重点、匹配岗位语言，让简历更像“为这个岗位写的”。

### 5. 保留排版，输出 Word

它会输出 Word 文档。如果你提供多份 `.docx` 简历，还可以选一份你最满意的版式作为样式参考，新简历会尽量复用那份排版。

## 安装

### 方式一：直接复制命令安装（推荐）

这是最简单的安装方式。

1. 在 Mac 上打开“终端”。
如果你不知道在哪里打开，可以按 `Command + Space`，输入“终端”，然后回车。
2. 复制下面这整段命令。
3. 粘贴到终端里。
4. 按一次回车，等待下载完成。
5. 重启 Claude Code。

```bash
mkdir -p ~/.claude/commands
curl -L https://raw.githubusercontent.com/rongmiao926-hub/claude-tailor-resume-command/main/.claude/commands/tailor-resume.md \
  -o ~/.claude/commands/tailor-resume.md
```

这段命令会自动把 `tailor-resume.md` 放到你的 `~/.claude/commands/` 目录里。

### 方式二：手动安装

如果你不想复制命令，也可以手动安装：

1. 点击这个仓库右上角的 `Code`。
2. 选择 `Download ZIP` 下载压缩包。
3. 解压后，打开里面的 `.claude/commands/` 文件夹。
4. 把其中的 `tailor-resume.md` 复制到你电脑上的 `~/.claude/commands/` 目录里。
5. 重启 Claude Code。

如果你不知道 `~/.claude/commands/` 在哪里：

1. 在 Finder 顶部菜单点 `前往`。
2. 选择 `前往文件夹...`。
3. 输入 `~/.claude/commands/`。
4. 把 `tailor-resume.md` 文件拖进去。

## 小白友好用法

装好以后，你只需要记住一件事：先写 `/tailor-resume`，然后像聊天一样告诉它“帮我改简历，我的简历放在哪，JD 放在哪”。

你可以像平时聊天一样写：

```text
/tailor-resume 帮我改简历。我的简历放在 ~/Documents/resumes/，这是一个增长运营岗位的 JD。请从我所有简历里找最匹配的经历，缺什么就问我，然后帮我生成一份一页中文简历。
```

```text
/tailor-resume 帮我改简历。我的简历放在 ~/Documents/resumes/，JD 链接放在这里：https://example.com/job/12345
```

```text
/tailor-resume 帮我改简历。我的简历放在 ~/Documents/resumes/，JD 截图都放在 ~/Documents/jd-screenshots/
```

```text
/tailor-resume 帮我改简历。我的简历放在 ~/Documents/resumes/，请沿用 ~/Documents/resumes/我最满意的简历.docx 的排版，然后针对下面这段 JD 改写：...
```

## 说明

- 只提供 PDF 简历时，通常只能复用内容，不能完整保留原排版。
- 如果一次给很多 JD，它会先识别岗位列表，再让你确认是否全部生成。
- 如果至少提供一份 `.docx` 简历，Word 输出效果通常更好。
