# 通用 MCU 开发 Skill

用于 STM32、ESP32、GD32 等 MCU 的 C/C++ 固件开发，适用于裸机和 RTOS 工程。
持续更新中～
## 安装与使用

下载仓库 ZIP 并解压，将含有 `SKILL.md` 的目录命名为 `embedded-architecture`，放入 Codex 的个人技能目录。在使用 `~/.codex/skills/` 的环境中，安装后的入口为 `~/.codex/skills/embedded-architecture/SKILL.md`。在 MCU 工程中打开新的 Codex 对话，可按下面的方式调用。

> 使用 $embedded-architecture 为 SPI 屏幕添加异步刷新。说明调用方什么时候可以复用像素缓冲区，并报告这次修改后的资源占用。

## 开发约定

- BSP 管理设备与外设，App 负责业务逻辑。两层独立于厂商生成代码，按实际芯片和 SDK 接入。
- SPI、I²C、CAN 等驱动按硬件能力和时限选用 DMA、中断、FIFO 或缓冲队列。接口写清传输完成条件、忙碌时的行为和缓冲区归属。
- 开发时补齐函数用途、数据单位及关键逻辑的源码注释，改码后同步纠正失效说明。
- 每次修改固件后，报告 CPU、RAM、Flash/ROM、栈和堆的占用及与可比基线的差值。内存以 KB 表示（1 KB = 1024 字节），运行指标注明测量条件，缺测项说明原因。

完整规则见 [SKILL.md](SKILL.md)，具体设计与测量方法见 [参考文档](references/)。
