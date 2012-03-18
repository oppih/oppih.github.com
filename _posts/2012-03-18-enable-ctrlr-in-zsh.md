---
layout: post
title: "Enable Ctrl+R (history search) in ZSH"
category: Note
tags: [zsh]
---
{% include JB/setup %}

用 ZSH 有几个月了，也好奇这个问题挺久了：ZSH（准确地说应该是oh-my-zsh）的默认配置居然不支持 Ctrl+R 来搜索历史命令。

今天在 Ruby China 会场，稍微开个小差，搜索了一下这个问题，找到了解决方法。 ZSH 支持搜索历史命令，不过需要自己 enable 一下， 在 ～/.zshrc 中添加：

    # Bacward search in the shell history with <C-r>
    bindkey '^R' history-incremental-search-backward
    setopt hist_ignore_all_dups

然后 `source ~/.zshrc` 就可以了。

----
稍微解释下？
`bindkey '^R' history-incremental-search-backward` 这个就是我们要实现的，
`setopt hist_ignore_all_dups` 呢，是从 [Gentoo 文档中 ZSH 部分](http://www.gentoo.org/doc/zh_cn/zsh.xml) 看来的：

> 为了防止记录重复的输入（比如`ls -l`在同一个shell会话中输入了太多次），你可以设置`hist_ignore_all_dups`选项