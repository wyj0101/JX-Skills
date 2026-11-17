# JX-Skills

个人可复用 Skill 库，按「办公 / 工作」两大类沉淀。

只收录在真实场景里跑通过、能反复复用的东西，不囤积半成品。

## 分类

| 目录 | 定位 | 内容示例 |
| --- | --- | --- |
| `office/` | 办公事务 | 文档/表格/汇报模板、PDF 处理、文件整理、会议与邮件 |
| `work/` | 工作能力 | 嵌入式软件开发全链路：平台、启动、驱动、RTOS、通信、构建、调试、协作、质量 |

以后遇到新领域再开新的一级分类，不硬塞进这两类。

## 目录结构

```
jx-skills/
├── README.md
├── office/
│   ├── docs/            方案、说明书、测试报告模板
│   ├── spreadsheet/     表格统计与数据整理
│   ├── slides/          汇报 PPT 模板
│   ├── pdf/             PDF 拆分、合并、转换
│   ├── file-tidy/       批量重命名与归档
│   └── meeting-email/   会议纪要、邮件模板
└── work/
    ├── mcu-platform/    芯片平台与最小系统（STM32/GD32/ESP32/NXP…）
    ├── boot/            启动流程、链接脚本、Flash 布局、OTA
    ├── drivers/         外设驱动（GPIO/定时器/串口/SPI/I2C/ADC/CAN/USB）
    ├── rtos/            FreeRTOS、RT-Thread、任务与同步机制
    ├── comm/            Modbus、CANopen/J1939、MQTT、BLE、自定义帧
    ├── build/           工具链、CMake/Makefile、交叉编译、CI、烧录脚本
    ├── debug-test/      J-Link/SWO、日志、单元测试、HardFault 定位、功耗测试
    ├── hw-collab/       引脚分配、原理图核对、时序与 EMC
    └── code-quality/    MISRA C、编码规范、代码评审清单
```

## Skill 目录约定

每个 Skill 一个子目录，目录名小写短横线：

```
work/drivers/uart-dma/
├── SKILL.md       # 用途、适用芯片、配置要点、坑
├── uart.c         # 可复用实现或片段
├── uart.h
└── example/       # 最小可运行示例
```

## SKILL.md 模板

```markdown
# <Skill 名称>

## 一句话说明
这个 Skill 解决什么问题。

## 适用场景
- ...

## 不适用场景
- ...

## 使用方式
1. ...

## 依赖与环境
- 芯片/工具链/版本：

## 踩过的坑
- ...
```

## 收录标准

1. 真实用过，至少在一个实际场景里跑通
2. 边界清晰，写清适用与不适用
3. 可独立复现，别人或半年后的自己拿到就能跑

## 添加流程

1. 在对应分类下新建 `<skill-name>/`
2. 按模板写 `SKILL.md`，放配套代码/脚本/模板
3. 本地验证跑通
4. 提交：`git add . && git commit -m "add: <分类>/<skill-name>" && git push`

## 维护约定

- 用不上的 Skill 果断删掉
- 每次重新使用后，把新踩的坑补回 `SKILL.md`
- 依赖外部环境或特定版本的，注明版本范围
