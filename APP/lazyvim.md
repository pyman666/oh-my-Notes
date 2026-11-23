
# 常用命令

首先要区分几个管理器有什么区别：

| 管理器 | 管理对象 | 例子 |
| --- | --- | --- |
| `:Lazy`       | Neovim 插件      | Flash、Treesitter、Which-Key  |
| `:LazyExtras` | LazyVim 功能组合 | Python 支持、调试、文件浏览器 |
| `:Mason`      | 外部开发工具     | Pyright、Prettier、Ruff       |


## 插件管理：Lazy

| 命令 | 功能 |
| --- | --- |
| `<leader>l`     | 打开插件管理界面         |
| `:Lazy`         | 打开插件管理界面         |
| `:Lazy sync`    | 安装、更新、清理插件     |
| `:Lazy update`  | 更新插件                 |
| `:Lazy install` | 安装缺失插件             |
| `:Lazy clean`   | 清理不再使用的插件       |
| `:Lazy check`   | 检查插件更新             |
| `:Lazy log`     | 查看插件更新日志         |
| `:Lazy profile` | 查看插件加载性能         |
| `:Lazy restore` | 恢复锁定文件中的插件版本 |
| `:Lazy reload`  | 重新加载插件配置         |


## Extra 管理：LazyExtras

LazyVim 将很多可选功能打包成 Extra。Extra 不等于单个插件，它通常是一组插件及其配置。

| 命令 | 功能 |
| --- | --- |
| `:LazyExtra`  | Extra 插件管理         |
| `:LazyHealth` | 加载插件并执行健康检查 |


## 工具管理：Mason

Mason 是 Neovim 的外部工具管理器。它管理的不是普通 Neovim 插件，而是编辑器依赖的外部程序安装。例如：

- LSP Server：语言服务器
- Formatter：代码格式化工具
- Linter：代码检查工具
- Debugger：调试工具

| 命令 | 功能 |
| --- | --- |
| `<leader>cm`              | 打开工具管理界面 |
| `:Mason`                  | 打开工具管理界面 |
| `:MasonInstall pyright`   | 安装 Python LSP  |
| `:MasonUninstall pyright` | 卸载工具         |
| `:MasonUpdate`            | 更新已安装工具   |
| `:MasonLog`               | 查看安装日志     |


# 常用功能

LazyVim 默认使用 `<Space>` 作为 Leader 键。下面按日常开发场景整理，主要是文件树、窗口、Buffer、Git、搜索、LSP。

下面是一些最基本的操作：

| 快捷键 | 功能 |
| --- | --- |
| `<leader>l`  | 打开 Lazy 插件管理器  |
| `<leader>L`  | 查看 LazyVim 更新日志 |
| `<leader>qq` | 退出 Neovim           |
| `:qa`        | 退出 Neovim           |
| `<C-/>`      | 打开/关闭终端         |
| `<leader>ft` | 打开终端              |
| `<leader>fT` | 打开根目录终端        |


## 一个特别有用的功能：Which-Key

强烈建议记住：LazyVim 不需要把所有快捷键背下来。直接按：

- `<leader>` 查看所有 Leader 快捷键。
- `<leader>sk` 搜索所有快捷键（Which-Key / Keymaps）。
- `<leader>?` 某些 LazyVim 版本或配置中可以查看帮助，具体以实际映射为准。

还有一个特别实用的技巧：**按下 Space 后先别按其他键，稍等一下。**LazyVim 默认集成 Which-Key，会弹出快捷键分组提示，告诉你接下来能按什么。


## 文件树（Neo-tree）

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


## 窗口切换与分屏

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
| `<C-h>` | 左侧窗口 |
| `<C-j>` | 下方窗口 |
| `<C-k>` | 上方窗口 |
| `<C-l>` | 右侧窗口 |

| `<C-↑>` | 增加高度 |
| `<C-↓>` | 减少高度 |
| `<C-←>` | 减少宽度 |
| `<C-→>` | 增加宽度 |

| `:split`     | 水平分屏    |
| `:vsplit`    | 垂直分屏    |
| `<C-w> s`    | 水平分屏    |
| `<C-w> v`    | 垂直分屏    |
| `<C-w> q`    | 关闭当前窗口|
| `<C-w> o`    | 关闭其他窗口|
| `<C-w> hjkl` | 上下左右窗口|


## Buffer 和文件切换

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


## Tab 管理

这里的 Tab 是 Neovim 的标签页，不是 Buffer。

| 快捷键 | 功能 |
| --- | --- |
| `<leader><tab><tab>` | 新建 Tab         |
| `<leader><tab>]`     | 下一个 Tab       |
| `<leader><tab>[`     | 上一个 Tab       |
| `<leader><tab>d`     | 关闭当前 Tab     |
| `<leader><tab>o`     | 关闭其他 Tab     |


## Quickfix / Location List

这两个是 Vim/Neovim 原生功能，LazyVim 提供快捷键入口。

| 快捷键 | 功能 |
| --- | --- |
| `<leader>xq` | 打开 Quickfix 列表 |
| `<leader>xl` | 打开 Location List |
| `]q`         | 下一个 Quickfix 项 |
| `[q`         | 上一个 Quickfix 项 |


# 代码编辑

LazyVim 保留了绝大多数 Vim 原生操作，对于部分操作作了增强，也通过插件和快捷键映射改变了部分行为。

| 操作 | 功能 |
| --- | --- |
| `<C-s>` | 保存文件（普通/插入模式均可）  |
| `<Esc>` | 退出当前模式，同时清除搜索高亮 |


## 文本对象增强：mini.ai

原生 Vim 有 `iw`、`as`、`ip`、`at`、`ib`、`aB` 等文本对象，LazyVim 通过 `mini.ai` 扩展了更多语法结构识别。

| 操作 | 功能 |
| --- | --- |
| `vaf` | 选择整个函数 |
| `vif` | 选择函数内部 |
| `vac` | 选择整个类   |
| `vic` | 选择类内部   |
| `vaa` | 选择整个参数 |
| `via` | 选择参数内部 |

这些是 mini.ai 的典型文本对象，具体支持情况取决于 Treesitter 配置。例如：

- `daf`：删除整个函数
- `yif`：复制函数内部
- `caa`：修改当前参数


## 自动括号与引号：mini.pairs

输入时自动补全成对符号。这是输入行为增强，不需要额外快捷键。


## Flash：快速定位

| 操作 | 功能 |
| --- | --- |
| `s`         | 屏幕范围快速跳转                |
| `S`         | Treesitter 结构跳转             |
| `r`         | Operator-pending 模式下远程跳转 |
| `R`         | Treesitter 范围搜索             |
| `<C-space>` | Treesitter 增量选择             |


## 移动与调整文本

| 操作 | 功能 |
| --- | --- |
| `<A-j>`          | 当前行向下移动     |
| `<A-k>`          | 当前行向上移动     |
| Visual + `<A-j>` | 选中行向下移动     |
| Visual + `<A-k>` | 选中行向上移动     |
| `=`              | 自动缩进           |
| `>>`             | 向右缩进           |
| `<<`             | 向左缩进           |
| Visual + `>`     | 缩进并保持选区     |
| Visual + `<`     | 反向缩进并保持选区 |

后两项是 LazyVim 对原生缩进行为的增强。


## Surround：包围符号编辑

如果启用了 `mini.surround`，可以使用：

| 操作 | 功能 |
| --- | --- |
| `gsa{motion}{char}` | 添加包围符号     |
| `gsd{char}`         | 删除包围符号     |
| `gsr{old}{new}`     | 替换包围符号     |
| `gsf{char}`         | 查找右侧包围符号 |
| `gsF{char}`         | 查找左侧包围符号 |


## Comment：注释增强

LazyVim 默认使用 `mini.comment` 插件提供注释功能（具体取决于 LazyVim 版本）。

| 快捷键 | 功能 |
| --- | --- |
| `gc{motion}` | 注释指定范围     |
| `gcc`        | 注释当前行       |
| `gco`        | 在下一行添加注释 |
| `gcO`        | 在上一行添加注释 |


# Git 操作

LazyVim 的 Git 工具分工：

| 工具 | 主要用途 | 类比 |
| --- | --- | --- |
| Snacks Git | Git Log、Blame、文件历史、GitHub 浏览        | Git 历史查询工具   |
| Gitsigns   | 行级变更、Hunk 操作                          | Git 局部操作工具   |
| LazyGit    | Commit、Push、Pull、Branch、Rebase、冲突处理 | Git 图形终端客户端 |
| Fugitive   | 在 Neovim 中执行 Git 操作                    | Git 命令接口       |
| Diffview   | 查看分支、Commit、文件之间的差异             | Diff 查看器        |

下面是 snacks.vim Git 操作：

| 快捷键 | 功能 |
| --- | --- |
| `<leader>gs` | Git Status                  |
| `<leader>gd` | 查看 Git Diff               |
| `<leader>gD` | 与远程分支比较 Diff         |
| `<leader>gl` | Git Log                     |
| `<leader>gL` | 当前目录 Git Log            |
| `<leader>gb` | 当前行 Git Blame            |
| `<leader>gf` | 当前文件历史                |
| `<leader>gB` | 浏览当前文件对应的 Git 页面 |

gitsigns.nvim 主要显示代码行（hunk）变更：

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

lazygit.nvim 负责交互，有独立的 Git TUI 界面，界面一般有 5 个面板，只要输入面板编号然后输入问号就可查看相关操作。

| 快捷键 | 功能 |
| --- | --- |
| `<leader>gg` | 打开 LazyGit     |
| `q`          | 退出 LazyGit     |
| `?`          | 帮助，查看快捷键 |
| `<Tab>`      | 切换到下一个面板 |
| `<S-Tab>`    | 切换到上一个面板 |
| `1`～`5`     | 直接切换对应面板 |
| `←` / `h`    | 切换到左侧面板   |
| `→` / `l`    | 切换到右侧面板   |
| `↑` / `k`    | 上一个项目       |
| `↓` / `j`    | 下一个项目       |


# 文件搜索与模糊查找

新版 LazyVim starter 默认用 snacks.nvim 当 picker，功能基本都走 `<leader>` 映射和 Lua 函数，很多网上常见的命令不再提供。

| 快捷键 | 功能 |
| --- | --- |
| `<leader><space>` | 查找文件          |
| `<leader>ff`      | 查找文件          |
| `<leader>fg`      | 全局文本搜索 Grep |
| `<leader>fb`      | 查找 Buffer       |
| `<leader>fr`      | 最近打开的文件    |
| `<leader>fc`      | 查找配置文件      |
| `<leader>fn`      | 新建文件          |

| `<leader>sg`      | 全局搜索          |
| `<leader>sc`      | 命令历史          |
| `<leader>sC`      | 所有命令          |
| `<leader>sr`      | 查找替换          |
| `<leader>sk`      | 搜索快捷键        |

搜索结果中通常可以使用：

- `Enter`：打开文件。
- `<C-x>`：水平分屏打开。
- `<C-v>`：垂直分屏打开。
- `<C-t>`：新 Tab 打开。


# LSP 代码导航

这是 LazyVim 最值得使用的部分之一。

| 快捷键 | 功能 |
| --- | --- |
| `gd` | 跳转定义          |
| `gD` | 跳转声明          |
| `gr` | 查找引用          |
| `gI` | 查找实现          |
| `gy` | 跳转类型定义      |
| `K`  | 查看文档/悬浮信息 |
| `gK` | 查看函数签名帮助  |

| `]d` | 下一个诊断 |
| `[d` | 上一个诊断 |
| `]e` | 下一个错误 |
| `]w` | 下一个警告 |

| `<leader>cf` | 格式化代码             |
| `<leader>cm` | Mason                  |
| `<leader>ca` | Code Action（需 LSP）  |
| `<leader>cr` | 重命名变量等（需 LSP） |


# UI

| 快捷键 | 功能 |
| --- | --- |
| `<leader>u`  | UI 设置切换         |
| `<leader>uC` | colorscheme         |
| `<leader>uz` | Zen Mode            |
| `<leader>uZ` | Zoom Mode           |
| `<leader>ul` | 显示/隐藏行号       |
| `<leader>uL` | 切换相对行号        |
| `<leader>un` | 显示/隐藏通知       |
| `<leader>uw` | 切换自动换行        |
| `<leader>us` | 切换拼写检查        |
| `<leader>ud` | 显示/隐藏诊断       |
| `<leader>ug` | 显示/隐藏缩进参考线 |
| `<leader>ur` | 重绘界面、清除高亮  |

