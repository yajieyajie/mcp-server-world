# mcp-server-world

A powerful MCP-server.

> 为没有 API 的传统软件，打造一个接入 AI 时代的万能插座。

[English](README.md) | [简体中文](README_zh.md)

## 💡 痛点背景 (Why)

目前的 MCP (Model Context Protocol) 生态，大多服务于有标准 API 的现代软件（如 GitHub、Slack、数据库等）。但对于大量没有 API 的传统软件、老旧的桌面 ERP、行业工具，大模型依然是“瞎子”。

现有的方案中，手写 RPA 脚本极其昂贵且极度脆弱；而每次操作都使用纯视觉大模型截图识别，又面临着极高的 Token 成本和长达数秒的延迟。

## 🚀 核心方案 (How)

本项目旨在构建一个通用的 MCP Server，为无 API 软件提供低成本的 GUI 操控能力。核心思路是“**大模型做宏观规划，本地/云工具做微观执行**”：

1. **大模型做宏观规划**：仅利用视觉大模型对界面进行一次性的整体分析，提取菜单栏、工具栏、编辑区等区域的相对坐标，生成“界面地图”。这解决了纯视觉识别 Token 成本高、延迟大的问题。
2. **微观执行（支持本地/云端双模式）**：
   - **本地模式（默认）**：使用 OpenCV 模板匹配 + 本地轻量级 OCR（如 PaddleOCR）进行精准定位，实现毫秒级响应，完全离线，**零 Token 成本，数据不外传**。适合对隐私和速度要求高的场景。
   - **云端模式（可选扩展）**：接入阿里云、腾讯云等 OCR API，作为本地识别失败时的补充，或满足对识别精度有更高要求的场景。
3. **跨端桥接**：将上述能力封装成标准的 MCP 工具，供 Claude、Cursor 等客户端无缝调用。

## 📂 项目现状 (Status)

目前项目处于**原型构思与 PoC (概念验证) 阶段**。
下一步计划验证“视觉大模型分区 + 本地精确定位”的基础链路。欢迎对无 API 软件自动化、AI Agent 操控现实世界感兴趣的朋友一起探讨，也欢迎提 Issue 分享你遇到的痛点。

## 👤 作者 (Author)

- **Ma Yajie (马亚杰)**

## 📄 开源协议 (License)

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
