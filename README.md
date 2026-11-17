# Blink

RoboMaster 电控组 32 阶段第一次培训 · 作业

## 完成情况

- [x] 基础 1：使用 `HAL_Delay` 实现 LED 500ms 闪烁
- [ ] 基础 2：不使用 `HAL_Delay` 实现 LED 500ms 闪烁
- [ ] 基础 3：按键（EXTI 中断）控制 LED，含 20ms 软件消抖
- [x] 基础 4：代码提交至 GitHub 仓库

进阶（选做）：

- [ ] 进阶 5：短按切换常亮/常灭，长按（≥1s）松手进入 5Hz 快闪
- [ ] 进阶 6：双击（间隔 <500ms）翻转

## 硬件

- 主控：STM32F103C8T6（Blue Pill 兼容板，8MHz 晶振）
- 下载器：ST-Link V2（SWD，Connect under Reset）
- 外接 LED：PA5 → 限流电阻 → LED → GND（推挽输出，高电平点亮）
- 按键：PA0（内部上拉，按下接地）

## 软件环境

- STM32CubeMX 6.18.1，固件包 STM32Cube_FW_F1_V1.8.7
- Keil MDK 5.43a，ARM Compiler 6（V6.24）
- 系统时钟：HSE 8MHz → PLL ×9 → SYSCLK 72MHz，AHB /1，APB1 /2，APB2 /1

## 目录说明

- `Core/`：CubeMX 生成的用户代码，作业逻辑写在 `Core/Src/main.c` 的 `USER CODE` 区
- `Drivers/`：ST HAL 库
- `MDK-ARM/`：Keil 工程（编译产物已通过 .gitignore 排除）
- `Blink.ioc`：CubeMX 工程配置，双击可直接打开
