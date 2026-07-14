---
title: GNU/Linux 桌面环境介绍
published: 2026-07-14
description: '本文以GTK和Qt两大工具包为线索，系统介绍了GNU/Linux主流桌面环境：GTK阵营包括简约的GNOME及其衍生版MATE（传统GNOME 2风格）、Cinnamon（融合现代与传统），以及轻量的Xfce和LXDE；Qt阵营涵盖功能丰富的KDE及其经典分支TDE，以及轻量模块化的LXQt。文章梳理了各环境的起源、特点与适用场景，为Linux用户提供了实用的参考指南。'
tags: [DE,桌面环境]
category: '教程'
draft: false
ai: '本文以GTK和Qt两大工具包为线索，系统介绍了GNU/Linux主流桌面环境：GTK阵营包括简约的GNOME及其衍生版MATE（传统GNOME 2风格）、Cinnamon（融合现代与传统），以及轻量的Xfce和LXDE；Qt阵营涵盖功能丰富的KDE及其经典分支TDE，以及轻量模块化的LXQt。文章梳理了各环境的起源、特点与适用场景，为Linux用户提供了实用的参考指南。'
---
众所周知，GNU/Linux 拥有许多桌面环境。今天就让我通过开发它们使用的工具包来介绍它们。
开发桌面环境的工具包主要有 2 个，分别是 GTK 和 Qt。

## 使用 GTK 开发的桌面环境

### GNOME

GNOME 是一个完全由自由软件组成的桌面环境，最初由 Miguel de Icaza 和 Federico Mena 于 1997年 发起，首个主要版本发布于 1999年。其设计目标是为 Linux 及其他类 Unix 系统提供一个功能完善、操作简单且界面友好的图形化工作环境，秉承“Less is More”的理念，强调简洁、直观和易用性。

在 GNOME 3 发布后，有一群人不满 GNOME 3 的设计，便从 GNOME 2 Fork 出来，形成了 MATE 桌面环境。

还有一群人，在 GNOME 3 Fork 出来，旨在保留 GNOME 2 的传统桌面布局，同时利用 GNOME 3的技术栈，形成了 Cinnamon 桌面环境。

#### MATE

MATE 桌面环境，由已经停止官方维护的 GNOME 2 源代码衍生而来。MATE 得名于南美植物巴拉圭冬青（yerba mate）。由于 GNOME 3 在界面上的激进变动，导致诸多批评，因而许多人决定创建一个 GNOME 的衍生桌面环境，维持 GNOME 2 的风格。

#### Cinnamon

Cinnamon是一款由 Linux Mint 团队开发的桌面环境，旨在为用户提供类似 GNOME 2 的传统、直观且高效的操作体验。它最初是 GNOME Shell 的衍生版本，自 2.0 版本起成为独立的桌面环境，底层基于 GTK+ 技术构建，兼具现代功能与传统布局。

### Xfce

Xfce 是一款专为 UNIX 及类 UNIX 操作系统（如 GNU/Linux、FreeBSD）设计的轻量级桌面环境。它由 Olivier Fourdan 于 1996 年创建，旨在提供快速、低资源消耗且美观实用的用户界面，特别适用于老旧硬件、低配置设备或对系统性能有较高要求的用户。

### LXDE

LXDE 桌面环境是一个专为 Unix/Linux/BSD 等 POSIX 兼容系统设计的模块化桌面环境，由台湾开发者洪任谕（PCMan）等人于 2006 年发起。其核心设计理念是轻量、快速和低资源占用，旨在为老旧计算机或资源受限设备提供高效的用户体验。

LXDE 采用模块化架构，各组件依赖极少且可独立运行，默认使用 Openbox 作为窗口管理器。主要组件包括 PCManFM 文件管理器、 LXPanel 任务栏、 LXAppearance 外观设置工具以及 Leafpad 文本编辑器等。它支持多语言、标准快捷键及标签式文件浏览，内存占用通常仅需约 100 MB。

## 使用 Qt 开发的桌面环境

### KDE

KDE 是一种运行于 GNU/Linux 等类 UNIX 操作系统及 Microsoft Windows 系统的自由图形桌面环境，始建于 1996 年 10 月，由德国开发者 Matthias Ettrich 发起，采用 Qt 程序库开发，旨在为用户提供易用的 Unix 工作站管理界面。

在 KDE 4 发布后，有一群人不满 KDE 4 的外观与操作，便从 KDE 3.5 Fork 出来，形成了 TDE 桌面环境。

#### TDE

Trinity Desktop Environment (TDE) 是一个专为类 Unix 系统设计的轻量级、自由开源的桌面环境，旨在保留经典的 KDE 3.5 外观与操作习惯，同时适配现代硬件。它于 2010 年作为 KDE 3.5 的分支诞生，最初由 Timothy Pearson 发起，现已发展为完全独立的项目，由全球志愿者社区维护。

### LXQt

LXQt（Lightweight Qt Desktop Environment）是一款轻量级、模块化的自由开源 GNU/Linux 桌面环境，旨在提供低资源占用、快速启动和高度可定制的使用体验。

LXQt 由 LXDE（基于 GTK+）的 Qt 移植版本与 Razor-qt 项目合并而成，于 2013 年启动，2014 年发布首个测试版，2018 年正式从 LXDE 独立。
