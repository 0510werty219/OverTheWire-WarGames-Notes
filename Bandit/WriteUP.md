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

## 友情链接

[配套命令合集](./Useful%20Command.md)

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

---

## 参考文献

1. [Bandit 官网](https://overthewire.org/wargames/bandit/)
2. [Linux 101](https://101.lug.ustc.edu.cn/Ch03/#cat)