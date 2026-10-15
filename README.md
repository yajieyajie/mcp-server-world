# mcp-server-world

A powerful MCP-server.

> A universal socket connecting no-API software to the AI era.

[English](README.md) | [简体中文](README_zh.md)

## 💡 Why

The current MCP (Model Context Protocol) ecosystem mainly serves modern software with standard APIs (e.g., GitHub, Slack, databases). However, for a large number of traditional software, legacy desktop ERPs, and industry tools without APIs, LLMs remain "blind."

Existing solutions like writing RPA scripts are extremely expensive and fragile, while using pure visual LLMs for every screenshot recognition faces high token costs and multi-second latency.

## 🚀 How

This project aims to build a universal MCP Server that provides low-cost GUI control for no-API software. The core philosophy is: **"Macro-planning by LLM, Micro-execution by Local/Cloud tools."**

1. **Macro-planning by LLM**: Use a visual LLM for a one-time overall analysis of the UI, extracting relative coordinates of the menu bar, toolbar, editor area, etc., to generate a "UI Map." This solves the high token cost and latency of pure visual recognition.
2. **Micro-execution (Local/Cloud Hybrid Mode)**:
   - **Local Mode (Default)**: Uses OpenCV template matching + lightweight local OCR (e.g., PaddleOCR) for precise positioning. Achieves millisecond response, fully offline, **zero token cost, and no data leakage**. Suitable for scenarios requiring high privacy and speed.
   - **Cloud Mode (Optional Extension)**: Integrates with Alibaba Cloud, Tencent Cloud, etc., OCR APIs as a supplement when local recognition fails, or for scenarios demanding higher recognition accuracy.
3. **Cross-platform Bridging**: Wraps the above capabilities into standard MCP tools, seamlessly callable by clients like Claude and Cursor.

## 📂 Status

Currently in the **prototype and PoC (Proof of Concept) stage**.
The next step is to validate the basic pipeline of "Visual LLM for region division + Local tools for precise positioning". We welcome discussions from anyone interested in no-API software automation and AI Agents controlling the real world. Feel free to open an Issue to share your pain points.

## 👤 Author

- **Ma Yajie**

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
