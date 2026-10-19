# Bandit 蒟蒻笔记

>**Bandit**
>
>The Bandit wargame is aimed at absolute beginners. It will teach the basics needed to be able to play other wargames.

---

## 目录

>[!Error]
>
>When finished this ```WriteUP.md```, please remember to finish this TOC.

---

## 环境配置

强烈建议使用 Linux 系统，Ubuntu 即可，无需 kali。

---

## 实验过程

>[!TIP]
>
><details>
><summary>
>写在游戏之前
></summary>
>
>$\;$
>
>这是一个不会主动保存进度的类肉鸽类游戏，强烈推荐在**本地存储**每一层的通关密码等信息，以防下次不得不从 Level 0 重来一遍。（若是巅峰留不住，那就重走来时路）
>
>正如每一个页面标题：```Level (X-1) -> Level X``` 所说，关于如何获取 ```Level X``` 的信息都在该页面上。
>
>在游玩过程中，你会遇到许多不知道该做什么的情况。**Don’t panic! Don’t give up!** 游玩此游戏的目的就是来学习这些基础命令。对于那些你不会用甚至从来没听过的命令，请使用 ```man <command>```, ```<command> --help``` 以及 ```help <command>``` 进行学习。如果仍然存疑，请使用浏览器或者 AI 去搜索学习。
>
>当然，在本文件夹下也有一个作者自己编写的非官方的 [命令合集](./Useful%20Command.md)。但其中只记录了相对基础的命令的相对基础的用法，以普遍理性而言
>
></details>

### Level 0

>[!NOTE]
>
>需要掌握的命令：
>
>```ssh```

在这一关中，你需要使用 ```bandit0/bandit0``` 连接到 bandit.labs.overthewire.org 的 $2220$ 端口

```bash
ssh -p 2220 bandit0@bandit.labs.overthewire.org
# ssh -p <port> <username>@<hostname>
```

等待一段时间，会提示让你输入密码：```bandit0```

>[!TIP]
>
>输入的密码不会回显

### Level 0 $\rightarrow$ Level 1

>[!NOTE]
>
>需要掌握的命令：
>
>```ls```、```cat```

>[!TIP]
>
>在这一关中，你需要在 **Level 0** 的基础上继续
>
>但在后续关卡中请先退出登录再重新使用下一关的账号和密码进行登录

下一关到密码存储在 ```home``` 目录中下 ```readme``` 文件中

列出 ```home``` 下的目录和文件

```bash
ls
```

发现有一个 ```readme``` 文件，查看其内容

```bash
cat readme
```

找到了 **Level 1** 的密码：

```text
6y2**************************hNR
```

### Level 1 $\rightarrow$ Level 2

下一关的密码存储在 ```home``` 目录中下 ```-``` 文件中

使用 **Level 1** 的账号密码登录

列出 ```home``` 下的目录和文件

```bash
ls
```

发现有一个 ```-``` 文件，查看其内容

```bash
cat ./-
```

找到了 **Level 2** 的密码：

```text
PK8**************************ToB
```

### Level 2 $\rightarrow$ Level 3

下一关的密码存储在 ```home``` 目录中下 ```--spaces in this filename--``` 文件中

使用 **Level 2** 的账号密码登录

列出 ```home``` 下的目录和文件

```bash
ls
```

发现有一个 ```--spaces in this filename--``` 文件，查看其内容

```bash
cat ./"--spaces in this filename--"
```

找到了 **Level 3** 的密码：

```text
7ZZ**************************PME
```

### Level 3 $\rightarrow$ Level 4

下一关的密码存储在 ```inhere``` 目录中的一个隐藏文件中。

使用 **Level 3** 的账号和密码登录

列出 ```home``` 下的目录和文件

```bash
ls
```

发现有一个 ```inhere``` 目录

列出 ```inhere``` 下的所有目录和文件

```bash
ls -al
```

发现有一个 ```...Hiding-From-You``` 文件，查看其内容

```bash
cat ./"...Hiding-From-You"
```

找到了 **Level 4** 的密码：

```text
xzT**************************AMq
```

### Level 4 $\rightarrow$ Level 5

>[!NOTE]
>
>需要掌握的命令：
>
>```file```

下一关的密码存储在 inhere 目录中唯一人类可读的文件里。

使用 **Level 4** 的账号和密码登录

列出 ```home``` 下的目录和文件

```bash
ls
```

发现有一个 ```inhere``` 目录

列出 ```inhere``` 下的所有目录和文件

```bash
ls -al
```

发现有 ```-file00```、```-file01``` $\cdots$ ```-file09```

查看这些文件的文件类型

```bash
file ./*
```

```text
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
```

发现只有 ```-file07``` 是 ASCII 文本文件，查看其内容

```bash
cat ./"-file07"
```

找到了 **Level 5** 的密码：

```text
6C7**************************IrG
```

### Level 5 $\rightarrow$ Level 6

>[!NOTE]
>
>需要掌握的命令：
>
>```find```

下一级的密码存储在 inhere 目录下的某个文件中，该文件具有以下所有属性：

1. 可读（人类可读）
2. 大小为 $1033$ 字节
3. 不可执行

使用 **Level 5** 的账号和密码登录

列出 ```home``` 下的目录和文件

```bash
ls
```

发现有一个 ```inhere``` 目录

列出 ```inhere``` 下的所有目录和文件

```bash
ls -al
```

我们会发现有 $20$ 个目录，分别是 ```maybehere00``` 到 ```maybehere19```。随便打开其中一个，发现里面有 $9$ 个文件，倘若每个文件夹都如此的话，一个个去找得看 $180$ 个文件，过于麻烦。所以我们直接使用 ```find``` 命令进行查找。（需要先回到 ```inhere``` 目录下）

```bash
find -type f -size 1033c ! -executable
# find <哪个目录，如果没有默认当前目录>
# -type f: 只看普通文件
# -size 1033c: 大小是 1033 字节
# ! -executable: 不可执行
```

>[!NOTE]
>
><details>
><summary>
>关于附加条件 <code>-type f</code>
></summary>
>
>$\;$
>
>Linux 的哲学之一是：“everything is a file”
>
>目录、设备、管道、链接 $\cdots\cdots$ 在文件系统里统统是“文件”，只是类型不同。```ls -l``` 输出行的第一个字符就是类型标识：
>
>| ```ls -l``` 首字母 | 文件类型 | 说明或示例 |
>|:-:|:-:|:-:|
>| - | 普通文件 | 最常见的文件，例如：README.md，图片 |
>| d | 目录文件 | 用于组织和管理文件，不存实际内容 |
>| l | 软链接文件 | 类似快捷方式 |
>| b | 块设备文件 | 磁盘、U盘支持随机读写 |
>| c | 字符设备文件 | 键盘、鼠标，仅支持顺序读写 |
>| p | 管道文件 | 用于进程间单向通信，先入先出 |
>| s | 套接字文件 | 用于进程间双向通信，常见于数据库或网络服连接 |
>
></details>

>[!NOTE]
>
><details>
><summary>
>关于附加条件 <code>-size 1033c</code>
></summary>
>
>$\;$
>
>在有附加条件 ```-size``` 时，会先进行取整规则运算
>
>设文件字节数 $S$、后缀单位 $U$，先算 $N = \operatorname{ceil}(S/U)$（向上取整），再拿 $N$ 和 $n$ 比。
>
>| 写法 | 等价的字节范围 | 说明 |
>|:-:|:-:|:-:|
>| ```-size nU``` | $(n-1)U < S \leq nU$ | 精确第 n 个 $U$ 单位 |
>| ```-size -nU``` | $S \leq (n-1)U$ | 严格小于第 n 个 $U$ 单位 |
>| ```-size +nU``` | $S > nU$ | 大于第 n 个 $U$ 单位 |
>
>| 后缀单位写法 | 后缀单位实际大小 | 备注 |
>|:-:|:-:|:-:|
>| $b$（默认）| $512$ 字节 | **$b$ 不是 $byte$** |
>| $c$ | $1$ 字节 | 不是默认 |
>| $w$ | $2$ 字节 | 几乎用不到 |
>| $k$ | $1024$ 字节 | 小写 |
>| $M$ | $1024^2$ 字节 | 大写 |
>| $G$ | $1024^4$ 字节 | 大写 |
>
></details>

>[!NOTE]
>
><details>
><summary>
>关于附加条件 <code>! -exectuable</code>
></summary>
>
>$\;$
>
>当我们使用命令 ```ls -l``` 列出文件和目录的详细信息时，第一列除了会输出文件类型所代表的字符（详情见笔记：“关于附加条件 ```type -f```”）还会输出三组每组三个字符的权限信息
>
>三组顺序是：所有者、同组用户和其他用户
>
>每组内部顺序是：rwx，如不具有相应权限则用 - 代替
>
>r: 可读
>
>w: 可更改
>
>x: 可执行（x 在对于普通文件就是是否可执行，对于目录则是是否可进入访问）
>
>所以不可执行即代表没有 x 位
>
><details>
><summary>
>其实执行位还有特殊变种 $\cdots$
></summary>
>
>$\;$
>
>特殊位不新增字符位置，而是直接**占用对应身份的 x 位那一格**：那个位置原本是 `x`，就被改写成小写 `s`/`t`；原本是 `-`，就被改写成大写 `S`/`T`。所以大小写是“原位状态”的显示器。
>
>| 显示 | 占用位置 | 特殊位状态 | **该位置原本的 x 位** | 完整例子 | 数字 |
>|:-:|:-:|:-:|:-:|:-:|:-:|
>| `s` | 属主 u | setuid 已置位 | **有**（原本是 `x`） | `-rwsr-xr-x` | 4755 |
>| `S` | 属主 u | setuid 已置位 | **无**（原本是 `-`） | `-rwSr--r--` | 4644 |
>| `s` | 属组 g | setgid 已置位 | **有**（原本是 `x`） | `drwxrwsr-x` | 2775 |
>| `S` | 属组 g | setgid 已置位 | **无**（原本是 `-`） | `-rw-r-Sr--` | 2644 |
>| `t` | 其他 o | sticky 已置位 | **有**（原本是 `x`） | `drwxrwxrwt` | 1777 |
>| `T` | 其他 o | sticky 已置位 | **无**（原本是 `-`） | `drwxrwxrwT` | 1766 |
>
>想了解更多关于权限位的知识：[Linux 权限位记法速查表](./Linux%20权限位记法速查表.md)
>
></details>
>
></details>

返回满足条件的文件的路径：

```text
./maybehere07/.file2
```

根据路径打开文件

```bash
cd ./maybehere07
cat ./".file2"
```

找到 **Level 6** 的密码：

```text
pXa**************************SBW
```

---

## 参考文献

1. [Bandit 官网](https://overthewire.org/wargames/bandit/)
2. [Linux 101](https://101.lug.ustc.edu.cn/Ch03/#cat)