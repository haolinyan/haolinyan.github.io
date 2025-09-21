---
title: 优雅地配置你的专属AI Terminal
published: 2025-09-20
description: ''
image: ''
tags: []
category: ''
draft: true
lang: ''
---
# 需求分析

我非常喜欢使用oh-my-zsh + claude-code在Terminal中进行使用，但因为工作需要，我需要频繁在多个新的机器（不同系统，例如ubuntu, debian, win, macOS）上使用terminal, 每次重复为这些机器安装配置oh-my-zsh + claude-code 这些非常麻烦，而且还涉及到claude-code API秘钥的管理问题，为了避免重复工作和秘钥管理问题，我想找到一种优雅的方式来配置我的terminal, 使得我可以在不同的机器上快速、方便地使用oh-my-zsh + claude-code.

# 方案设计

提供一个bash脚本，该脚本可以自动安装oh-my-zsh + claude-code, 并配置好环境变量和API秘钥.

技术路线：
1. 首先支持自动安装zsh + oh-my-zsh 插件，要求跨平台（ubuntu, debian, win, macOS）

# 方案实现

# 测试




