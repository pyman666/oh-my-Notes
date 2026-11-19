LazyVim 默认使用 `<Space>` 作为 Leader 键。下面按日常开发场景整理，主要是文件树、窗口、Buffer、Git、搜索、LSP。


# **1. 文件树（Neo-tree）**

LazyVim 默认文件树插件是 neo-tree.nvim。

| 快捷键 | 功能 |
| --- | --- |
| `<leader> e` | 打开/关闭文件树          |
| `<leader> E` | 在当前文件位置打开文件树 |
| `Enter`      | 打开文件或展开目录       |
| `a`          | 新建文件/目录            |
| `d`          | 删除                     |
| `r`          | 重命名                   |
| `y`          | 复制文件                 |
| `x`          | 剪切文件                 |
| `p`          | 粘贴文件                 |
| `c`          | 复制文件路径             |
| `m`          | 移动文件                 |
| `H`          | 显示隐藏文件             |
| `R`          | 刷新文件树               |
| `?`          | 查看帮助                 |
| `q`          | 关闭文件树               |

注意：Neo-tree 的快捷键和普通 Vim 模式下的快捷键不是一回事，进入文件树后才能使用。


# **2. 窗口切换与分屏**

LazyVim 默认把 `<leader>w` 作为 Windows（窗口管理）快捷键组，而且它通过 Which-Key 映射了一批 Vim 原生的 `Ctrl+w` 操作。

| 快捷键/命令 | 功能 |
| --- | --- |
| `<leader> -`    | 水平分屏              |
| `<leader> \|`   | 垂直分屏              |
| `<leader>ws`    | 水平分屏              |
| `<leader>wv`    | 垂直分屏              |
| `<leader>wd`    | 关闭窗口，不删 Buffer |
| `<leader>wq`    | 关闭窗口，不删 Buffer |
| `<leader>wo`    | 关闭其他窗口          |
| `<leader>ww`    | 切换到上一窗口        |
| `<leader>whjkl` | 切换到上下左右侧窗口  |
| `<leader>w=`    | 平均窗口大小          |
| `<leader>wm`    | 最大化/恢复窗口 Zoom  |

**原生操作**

| 快捷键 | 功能 |
| --- | --- |
| `<C-↑>` | 增加高度 |
| `<C-↓>` | 减少高度 |
| `<C-←>` | 减少宽度 |
| `<C-→>` | 增加宽度 |
| `<C-h>` | 左侧窗口 |
| `<C-j>` | 下方窗口 |
| `<C-k>` | 上方窗口 |
| `<C-l>` | 右侧窗口 |

| `:split`     | 水平分屏    |
| `:vsplit`    | 垂直分屏    |
| `<C-w> s`    | 水平分屏    |
| `<C-w> v`    | 垂直分屏    |
| `<C-w> q`    | 关闭当前窗口|
| `<C-w> o`    | 关闭其他窗口|
| `<C-w> hjkl` | 上下左右窗口|


# **3. Buffer 和文件切换**

LazyVim 默认使用 Bufferline 显示打开的文件标签。这里要区分：

- Buffer：已经打开的文件。
- Window：显示 Buffer 的窗口。
- Tab：Neovim 的标签页布局，可以包含多个 Window。

日常开发主要使用 Buffer 和 Window，不必频繁使用 Tab。

| 快捷键 | 功能 |
| --- | --- |
| `H`          | 顺序遍历上一个 Buffer                   |
| `L`          | 顺序遍历下一个 Buffer                   |
| `<leader>bb` | 切换到上一个 Buffer，两个 Buffer 轮询   |
| `<leader>bd` | 关闭当前 Buffer，其他窗口布局尽可能保留 |
| `<leader>bD` | 关闭当前 Buffer 和 Window               |
| `<leader>bo` | 关闭其他 Buffer                         |
| `<leader>bi` | 关闭不可见 Buffer                       |
| `<leader>bp` | 固定当前 Buffer                         |


# **4. Git 操作**

LazyVim 默认集成了 LazyVim Git integration，主要涉及两个插件：

- gitsigns.nvim：显示代码行变更。
- lazygit.nvim：Git 交互管理。


## **Gitsigns**

| 快捷键 | 功能 |
| --- | --- |
| `]h`          | 下一个变更块         |
| `[h`          | 上一个变更块         |
| `<leader>ghs` | 暂存当前变更块       |
| `<leader>ghr` | 撤销当前变更块       |
| `<leader>ghS` | 暂存整个文件         |
| `<leader>ghR` | 撤销整个文件变更     |
| `<leader>ghp` | 预览当前变更块       |
| `<leader>ghd` | 查看当前文件 Diff    |
| `<leader>ghb` | 查看当前行 Git Blame |


## **LazyGit**

LazyGit 是独立的 Git TUI 界面，进入之后主要用方向键、Tab 和对应字母操作。

| 快捷键 | 功能 |
| --- | --- |
| `<leader>gg` | 打开 LazyGit      |
| `Space`      | 暂存/取消暂存文件 |
| `c`          | Commit            |
| `P`          | Push              |
| `p`          | Pull              |
| `b`          | 切换分支面板      |
| `n`          | 新建分支          |
| `?`          | 帮助              |


# **5. 文件搜索与模糊查找**

LazyVim 默认集成 Telescope.nvim，部分版本或配置也可能使用 Snacks Picker。

| 快捷键 | 功能 |
| --- | --- |
| `<leader><space>` | 查找文件          |
| `<leader>ff`      | 查找文件          |
| `<leader>fg`      | 全局文本搜索 Grep |
| `<leader>fb`      | 查找 Buffer       |
| `<leader>fr`      | 最近打开的文件    |
| `<leader>fc`      | 查找配置文件      |
| `<leader>sg`      | 全局搜索          |
| `<leader>sw`      | 搜索光标所在单词  |
| `<leader>sk`      | 搜索快捷键        |

搜索结果中通常可以使用：

- `Enter`：打开文件。
- `<C-x>`：水平分屏打开。
- `<C-v>`：垂直分屏打开。
- `<C-t>`：新 Tab 打开。


# **6. LSP 代码导航**

这是 LazyVim 最值得使用的部分之一。

| 快捷键 | 功能 |
| --- | --- |
| `gd`         | 跳转定义          |
| `gD`         | 跳转声明          |
| `gr`         | 查找引用          |
| `gI`         | 查找实现          |
| `gy`         | 跳转类型定义      |
| `K`          | 查看文档/悬浮信息 |
| `<leader>ca` | Code Action       |
| `<leader>cr` | 重命名            |
| `<leader>cf` | 格式化代码        |
| `<leader>cd` | 查看当前诊断      |
| `]d`         | 下一个诊断        |
| `[d`         | 上一个诊断        |


# **7. 其他常用功能**

| 快捷键 | 功能 |
| --- | --- |
| `<leader>l`  | Lazy 插件管理  |
| `<leader>u`  | UI 设置切换    |
| `<leader>qq` | 退出 Neovim    |
| `<leader>fn` | 新建文件       |
| `<leader>ft` | 打开终端       |
| `<leader>fT` | 打开根目录终端 |
| `<leader>ud` | 切换诊断显示   |
| `<leader>uf` | 切换自动格式化 |
| `<leader>us` | 切换拼写检查   |
| `<leader>ut` | 切换透明背景   |


# **8. 最重要：查看 LazyVim 全部快捷键**

其实没必要死记硬背。建议记住：

- `<leader>sk` 搜索所有快捷键（Which-Key / Keymaps）。
- `<leader>?` 某些 LazyVim 版本或配置中可以查看帮助，具体以实际映射为准。

还有一个特别实用的技巧：**按下 Space 后先别按其他键，稍等一下。**LazyVim 默认集成 Which-Key，会弹出快捷键分组提示，告诉你接下来能按什么。


## **建议先掌握这 15 个快捷键**

| 快捷键 | 用途 |
| --- | --- |
| `<leader>e`       | 文件树        |
| `<leader><space>` | 文件搜索      |
| `<leader>fg`      | 全局搜索      |
| `Ctrl+h/j/k/l`    | 窗口切换      |
| `<leader> -`      | 水平分屏      |
| `<leader> \|`     | 垂直分屏      |
| `H`               | 上一个文件    |
| `L`               | 下一个文件    |
| `<leader>bd`      | 关闭文件      |
| `<leader>gg`      | LazyGit       |
| `<leader>ghd`     | 查看 Git Diff |
| `gd`              | 跳转定义      |
| `gr`              | 查找引用      |
| `<leader>cr`      | 重命名        |
| `<leader>l`       | 插件管理      |

