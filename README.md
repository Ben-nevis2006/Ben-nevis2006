# 李浩东｜Haodong Li

大连海事大学电子信息科学与技术专业 2024 级本科生，求职方向涵盖嵌入式软件开发、汽车电子 / ECU 测试、嵌入式 / MCU 软件测试，以及硬件 Bring-up 与验证。

目前重点实践 STM32、FreeRTOS、CAN、外设联调与分阶段验证，覆盖从物料/器件身份核对、焊接与线束搭建、受控上电和 Flash 烧录，到 HAL 外设配置、RTOS 任务/IPC 基线、运行日志和仪器测量。我习惯把设计状态、构建结果和实物验证结论分开记录，让项目中的每项技术主张都能回到代码、配置或阶段文档。

## Featured Project

### [STM32 + FreeRTOS 双 ECU CAN 实时通信与故障检测原型](https://github.com/Ben-nevis2006/stm32-freertos-dual-ecu-can-diagnostics)

面向汽车热管理场景构建的双节点嵌入式原型：Node B 负责温控策略、Cooling Demand 与系统模式，Node A 负责风扇执行、反馈和本地保护。

当前状态（2026-10-25）：

- 已建立 Node A / Node B 两套 STM32F103RBT6 工程，完成外设、FreeRTOS 10.3.1 与 CMSIS-RTOS2 配置基线；
- **H1 实板 Bring-up PASS：**两块 NUCLEO 已完成独立 USB 枚举、目标识别、Flash 访问和稳定性验证；
- **H2 低压 CAN 物理链路 PASS：**两节点完成 `500 kbit/s` 正式帧收发、收发计数和受控断线/恢复验收；
- **H3 单外设部分关闭：**Node B NTC ADC、Node A `25 kHz` Fan PWM 档位以及 Tach `PPR=2` / RPM 新鲜度均已完成实板验证；
- **INA260 保持 HARDWARE HOLD：**已用无源检查、3.3 V 静态电平、全地址扫描、模块排针波形和电脑端复扫将故障收敛为模块级无 ACK；等待替换件后从 `INA-03A` 重新准入。

> 项目仍在持续开发。H1/H2 和 H3 已关闭子项有实板证据；整个 H3、闭环控制、CAN RPM 正常链路与故障注入仍不得提前声称通过。

### Evidence Navigation

- [当前有效文档索引](https://github.com/Ben-nevis2006/stm32-freertos-dual-ecu-can-diagnostics/tree/main/current)
- [H0 硬件验收基线](https://github.com/Ben-nevis2006/stm32-freertos-dual-ecu-can-diagnostics/blob/main/current/05_verification_gates_%E9%AA%8C%E8%AF%81%E4%B8%8E%E9%97%A8%E7%A6%81/Gate_H0_Hardware_Acceptance_Baseline_H0%E7%A1%AC%E4%BB%B6%E9%AA%8C%E6%94%B6%E5%9F%BA%E7%BA%BF_2026-09-22.md)
- [H1 NUCLEO USB Bring-up 执行记录](https://github.com/Ben-nevis2006/stm32-freertos-dual-ecu-can-diagnostics/blob/main/current/05_verification_gates_%E9%AA%8C%E8%AF%81%E4%B8%8E%E9%97%A8%E7%A6%81/Gate_H1_NUCLEO_USB_Bringup_Execution_Record_H1_NUCLEO_USB%E8%81%94%E8%B0%83%E6%89%A7%E8%A1%8C%E8%AE%B0%E5%BD%95_2026-09-24.md)
- [H2 CAN 物理层验收与排障证据](https://github.com/Ben-nevis2006/stm32-freertos-dual-ecu-can-diagnostics/blob/main/current/05_verification_gates_%E9%AA%8C%E8%AF%81%E4%B8%8E%E9%97%A8%E7%A6%81/Gate_H2_CAN_Physical_Layer_Execution_Record_H2_CAN%E7%89%A9%E7%90%86%E5%B1%82%E6%89%A7%E8%A1%8C%E8%AE%B0%E5%BD%95_2026-10-02.md)
- [H2 CAN 联调排障证据复盘](https://github.com/Ben-nevis2006/stm32-freertos-dual-ecu-can-diagnostics/blob/main/current/06_engineering_recaps_%E5%B7%A5%E7%A8%8B%E5%A4%8D%E7%9B%98/H2_CAN_Bringup_Troubleshooting_Evidence_Recap_H2_CAN%E8%81%94%E8%B0%83%E6%8E%92%E9%9A%9C%E8%AF%81%E6%8D%AE%E5%A4%8D%E7%9B%98_2026-10-07.md)
- [H3 单外设验证执行记录](https://github.com/Ben-nevis2006/stm32-freertos-dual-ecu-can-diagnostics/blob/main/current/05_verification_gates_%E9%AA%8C%E8%AF%81%E4%B8%8E%E9%97%A8%E7%A6%81/Gate_H3_Single_Peripheral_Validation_Execution_Record_H3%E5%8D%95%E5%A4%96%E8%AE%BE%E9%AA%8C%E8%AF%81%E6%89%A7%E8%A1%8C%E8%AE%B0%E5%BD%95_2026-10-07.md)
- [INA260 电脑端复位复扫原始证据](https://github.com/Ben-nevis2006/stm32-freertos-dual-ecu-can-diagnostics/tree/main/evidence/software/H3/2026-10-21)
- [Node A 固件工程](https://github.com/Ben-nevis2006/stm32-freertos-dual-ecu-can-diagnostics/tree/main/firmware/node_a)
- [Node B 固件工程](https://github.com/Ben-nevis2006/stm32-freertos-dual-ecu-can-diagnostics/tree/main/firmware/node_b)
- [项目提交历史](https://github.com/Ben-nevis2006/stm32-freertos-dual-ecu-can-diagnostics/commits/main)

## Capability Map

- **Embedded Software Development:** C、STM32F103RBT6、STM32CubeMX / CubeIDE、HAL；配置 GPIO、CAN、UART、ADC、I2C、TIM PWM 与 Input Capture，建立 FreeRTOS / CMSIS-RTOS2 Task 与 Queue / Mailbox 基线，并使用 IDE 生成 Makefile 完成 clean build。
- **Automotive Electronics / ECU Test:** 双 ECU 职责分工及 SAD、CAN Matrix、Fault List、FreeRTOS Task Architecture 受控设计基线；按 H1/H2 和 H3 已关闭子项推进低压原型 Gate 验证。
- **Embedded / MCU Software Test:** 结合构建/刷写、UART 日志和受控刺激验证 CAN、NTC、PWM、Tach/RPM 路径，保留失败样本、修复与复验结论。
- **Hardware Bring-up & Validation:** 物料/器件身份核对、排针焊接、线束/面包板搭建、上电前连续性/阻值/极性检查、双板 Bring-up 与 Flash 写入/校验；使用万用表、示波器、ST-LINK 与 CubeProgrammer。
- **CAN / System Integration & Verification:** 完成 `500 kbit/s` 双向 CAN 正式帧和受控断线/恢复验证；按 `MCU TX → SLNT → CANH/CANL → RX → UART` 分层测点定位焊接、跳线和接触问题。
- **Engineering Documentation:** 结合 ST / NXP / TI 英文 datasheet 核对引脚、电气边界、接口与地址；使用 Git/GitHub 维护受控设计文档、Gate 记录、原始日志和证据索引。

## Working Principles

- 用版本记录保存设计决策、配置基线和阶段交接；
- 区分“已经实现”“已经构建”“已经设计”和“尚待实测”；
- 为关键结论保留源码、配置、文档或测试记录入口；
- 先建立可复现的最小闭环，再补充定量性能与故障验证；
- 个人负责实物清点、焊接/接线、上断电、仪器测量、故障刺激与结果确认；工具辅助资料检索、固件迭代、构建/刷写、日志解析和文档整理。

