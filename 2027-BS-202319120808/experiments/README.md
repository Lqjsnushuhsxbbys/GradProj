# experiments 目录说明与实验记录规范

## 目录强制规范

- `baseline/`：裸机轮询 Baseline（EXP-001）；
- `exp01/`、`exp02/` …：每个实验一个独立目录，目录内必须包含实验记录 `README.md`；
- 实验相关的配置快照、脚本、原始数据可随目录存放，最终汇总数据/图表放 `results/`；
- EXP 编号全局唯一，实验设计与计划编号见 `docs/03-design/experiment_design.md`：

| 目录 | Experiment | 内容 |
|---|---|---|
| baseline/ | EXP-001 | 裸机轮询 Baseline 性能摸底 |
| exp01/ | EXP-002 | FreeRTOS 任务响应时间与采样周期稳定性 |
| exp02/ | EXP-003 | MQTT 延迟与成功率 |
| exp03/ | EXP-004 | 超限报警响应时间（目录在实验启动时创建） |
| exp04/ | EXP-005 | 异常工况测试（目录在实验启动时创建） |

## 实验记录模板（每个实验必须照此填写）

```markdown
# Experiment ID

EXP-001

## Purpose

验证……

## Compared with

Baseline

## Configuration

...

## Dataset

...

## Random seed

...

## Command

...

## Result

...

## Conclusion

...

## Problems

...
```

## 基本要求

1. Configuration 必须写清硬件型号与连接、固件版本/commit、FreeRTOS 参数、Broker、网络环境、测试工具；
2. Result 必须给出原始数据路径（`results/` 或本目录）与统计方法、样本量；
3. 结论只陈述本实验数据支持的事实，不夸大；
4. 出现异常数据必须在 Problems 中说明原因或标记复测；
5. 任何实验失败也必须保留记录，不得删除（可追加“已作废”说明并指向新实验）。
