# Useful Command in Bandit

---

## 目录

>[!Error]
>
>When finished this ```WriteUP.md```, please remember to finish this TOC.

---

## ssh

>安全外壳协议（Secure Shell Protocol，简称 SSH）是一种加密的网络传输协议，可在不安全的网络中为网络服务提供安全的传输环境。SSH 通过在网络中建立安全隧道来实现SSH客户端与服务器之间的连接。
><p align="right"> —— 维基百科</p>

### 基本用法

```bash
ssh <username>@<hostname>
# 使用指定用户名连接到指定远程主机
```

### 指定端口进行连接

```bash
ssh -p <port> <username>@<hostname>
```

### 通过密钥文件进行连接

```bash
ssh -i <path to private key> <username>@<hostname>
```

## ls

>ls 命令用于查看文件夹中的内容

### 基本用法

```bash
ls
# 列出当前文件夹中的内容
```

```bash
ls <path to directory>
# 列出指定文件夹中的内容
```

### 常用参数

```bash
-a # 显示文件夹下所有内容包括隐藏文件和隐藏文件夹
-l # 以列表的形式输出文件的详细信息
```

## cat

>cat 命令用于输出文件内容

```bash
cat <file 1> [ <file 2> <file 3> ... <file n> ]
# 输出 file 1 （与 file 2 一直到 file n 拼接）的结果
```

## touch

>touch 命令用于创建文件

```bash
touch file.txt
# 在当前文件夹下创建一个名为 file 的 txt 文件
```

## nano

>nano 命令用于编辑文件（如果没有则创建）

```bash
nano file.txt
# 使用 nano 编辑 file.txt 文件（如果没有则创建）
```

---

## 参考文献

1. [Linux 101](https://101.lug.ustc.edu.cn/Ch03/#cat)