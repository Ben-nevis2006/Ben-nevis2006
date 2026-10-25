# 李浩东｜Haodong Li

大连海事大学电子信息科学与技术专业 2024 级本科生，求职方向为汽车电子测试、嵌入式测试与嵌入式软件实习。

目前重点实践 STM32、FreeRTOS、CAN 与故障处理设计。我习惯把设计状态、构建结果和实物验证结论分开记录，让项目中的每项技术主张都能回到代码、配置或阶段文档。

## Featured Project

### [STM32 + FreeRTOS 双 ECU CAN 热管理控制系统](https://github.com/Ben-nevis2006/stm32-freertos-dual-ecu-can-diagnostics)

面向汽车热管理场景构建的双节点嵌入式项目：Node B 负责温控策略、Cooling Demand 与系统模式，Node A 负责风扇执行、反馈和本地保护。

当前状态（2026-10-25）：

- 已建立 Node A / Node B 两套 STM32F103RBT6 工程，完成外设、FreeRTOS 10.3.1 与 CMSIS-RTOS2 配置基线；
- **H1 实板 Bring-up PASS：**两块 NUCLEO 已完成独立 USB 枚举、目标识别、Flash 访问和稳定性验证；
- **H2 低压 CAN 物理链路 PASS：**两节点完成 `500 kbit/s` 正式帧收发、收发计数和受控断线/恢复验收；
- **H3 单外设部分关闭：**Node B NTC ADC、Node A `25 kHz` Fan PWM 档位以及 Tach `PPR=2` / RPM 新鲜度均已完成实板验证；
- **INA260 保持 HARDWARE HOLD：**已用无源检查、3.3 V 静态电平、全地址扫描、模块排针波形和电脑端复扫将故障收敛为模块级无 ACK；等待替换件后从 `INA-03A` 重新准入。

> 项目仍在持续开发。H1/H2 和 H3 已关闭子项有实板证据；整个 H3、闭环控制、CAN RPM 正常链路与故障注入仍不得提前声称通过。

### Evidence Navigation

- [当前有效文档索引](https://github.com/Ben-nevis2006/stm32-freertos-dual-ecu-can-diagnostics/tree/main/current)
- [H1 NUCLEO USB Bring-up 执行记录](https://github.com/Ben-nevis2006/stm32-freertos-dual-ecu-can-diagnostics/blob/main/current/05_verification_gates_%E9%AA%8C%E8%AF%81%E4%B8%8E%E9%97%A8%E7%A6%81/Gate_H1_NUCLEO_USB_Bringup_Execution_Record_H1_NUCLEO_USB%E8%81%94%E8%B0%83%E6%89%A7%E8%A1%8C%E8%AE%B0%E5%BD%95_2026-09-24.md)
- [H2 CAN 物理层验收与排障证据](https://github.com/Ben-nevis2006/stm32-freertos-dual-ecu-can-diagnostics/blob/main/current/05_verification_gates_%E9%AA%8C%E8%AF%81%E4%B8%8E%E9%97%A8%E7%A6%81/Gate_H2_CAN_Physical_Layer_Execution_Record_H2_CAN%E7%89%A9%E7%90%86%E5%B1%82%E6%89%A7%E8%A1%8C%E8%AE%B0%E5%BD%95_2026-10-02.md)
- [H3 单外设验证执行记录](https://github.com/Ben-nevis2006/stm32-freertos-dual-ecu-can-diagnostics/blob/main/current/05_verification_gates_%E9%AA%8C%E8%AF%81%E4%B8%8E%E9%97%A8%E7%A6%81/Gate_H3_Single_Peripheral_Validation_Execution_Record_H3%E5%8D%95%E5%A4%96%E8%AE%BE%E9%AA%8C%E8%AF%81%E6%89%A7%E8%A1%8C%E8%AE%B0%E5%BD%95_2026-10-07.md)
- [INA260 电脑端复位复扫原始证据](https://github.com/Ben-nevis2006/stm32-freertos-dual-ecu-can-diagnostics/tree/main/evidence/software/H3/2026-10-21)
- [Node A 固件工程](https://github.com/Ben-nevis2006/stm32-freertos-dual-ecu-can-diagnostics/tree/main/firmware/node_a)
- [Node B 固件工程](https://github.com/Ben-nevis2006/stm32-freertos-dual-ecu-can-diagnostics/tree/main/firmware/node_b)
- [项目提交历史](https://github.com/Ben-nevis2006/stm32-freertos-dual-ecu-can-diagnostics/commits/main)

## Technical Focus

- **MCU / Toolchain:** STM32F103RBT6, STM32CubeMX, STM32CubeIDE, HAL
- **RTOS / IPC:** FreeRTOS, CMSIS-RTOS2, Task, Queue, latest-state Mailbox
- **Communication / Peripherals:** CAN, UART, ADC, PWM, Input Capture, I2C
- **Engineering:** Embedded C, Git/GitHub, CAN Matrix, Fault List, oscilloscope/DMM bring-up, staged verification

## Working Principles

- 用版本记录保存设计决策、配置基线和阶段交接；
- 区分“已经实现”“已经构建”“已经设计”和“尚待实测”；
- 为关键结论保留源码、配置、文档或测试记录入口；
- 先建立可复现的最小闭环，再补充定量性能与故障验证。

