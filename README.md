[README.md](https://github.com/user-attachments/files/32456504/README.md)
# 李浩东｜Haodong Li

大连海事大学电子信息科学与技术专业 2024 级本科生，求职方向为汽车电子测试、嵌入式测试与嵌入式软件实习。

目前重点实践 STM32、FreeRTOS、CAN 与故障处理设计。我习惯把设计状态、构建结果和实物验证结论分开记录，让项目中的每项技术主张都能回到代码、配置或阶段文档。

## Featured Project

### [STM32 + FreeRTOS 双 ECU CAN 热管理控制系统](https://github.com/Ben-nevis2006/stm32-freertos-dual-ecu-can-diagnostics)

面向汽车热管理场景构建的双节点嵌入式项目：Node B 负责温控策略、Cooling Demand 与系统模式，Node A 负责风扇执行、反馈和本地保护。

当前状态（2026-09-21）：

- 已建立 Node A / Node B 两套 STM32F103RBT6 工程，完成外设、FreeRTOS 10.3.1 与 CMSIS-RTOS2 配置基线；
- 已创建 5 个任务和 5 个 Queue/Mailbox IPC 对象，两节点阶段构建记录均为 `0 errors / 0 warnings`；
- 已形成 SAD、Fault List、CAN Matrix 与 FreeRTOS Task Architecture 等设计基线；
- 正在推进两板 Bring-up、CAN 基础收发、传感器/执行器联调、闭环控制及故障注入验证。

> 项目仍在持续开发。当前构建结果不等同于目标板运行、实时性或硬件功能已经验证。

### Evidence Navigation

- [当前有效文档索引](https://github.com/Ben-nevis2006/stm32-freertos-dual-ecu-can-diagnostics/tree/main/current)
- [硬件到货阶段交接与基线汇总](https://github.com/Ben-nevis2006/stm32-freertos-dual-ecu-can-diagnostics/blob/main/current/Hardware_Arrival_Transition_Report_2026-09-17.md)
- [Node A 固件工程](https://github.com/Ben-nevis2006/stm32-freertos-dual-ecu-can-diagnostics/tree/main/firmware/node_a)
- [Node B 固件工程](https://github.com/Ben-nevis2006/stm32-freertos-dual-ecu-can-diagnostics/tree/main/firmware/node_b)
- [项目提交历史](https://github.com/Ben-nevis2006/stm32-freertos-dual-ecu-can-diagnostics/commits/main)

## Technical Focus

- **MCU / Toolchain:** STM32F103RBT6, STM32CubeMX, STM32CubeIDE, HAL
- **RTOS / IPC:** FreeRTOS, CMSIS-RTOS2, Task, Queue, latest-state Mailbox
- **Communication / Peripherals:** CAN, UART, ADC, PWM, Input Capture, I2C
- **Engineering:** Embedded C, Git/GitHub, CAN Matrix, Fault List, staged verification

## Working Principles

- 用版本记录保存设计决策、配置基线和阶段交接；
- 区分“已经实现”“已经构建”“已经设计”和“尚待实测”；
- 为关键结论保留源码、配置、文档或测试记录入口；
- 先建立可复现的最小闭环，再补充定量性能与故障验证。

