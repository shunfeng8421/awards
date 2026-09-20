# JSP-000301 提交前自查报告（lean-verify self-check）

> 生成：2026-09-20。依据官方 `skills/lean-verify` 规范（PR #1759 已合并，要求 Lean 提交附 pre-submission self-check）。
> 报告人：Shiqiang Chen（shunfeng8421）。

## 结论

> **总体结论：验证通过（公理干净）。**
> 对于 JSP-000301，在证明仓库 `shunfeng8421/jsp301-lean` commit `9bc23f0` 上，
> 该提交的 Lean 目标声明 `Jsp301.JSP_301` 已通过编译与公理审计，
> 且按 lean-verify 规范无 native_decide 扩展信任，仅依赖标准三项公理（或更少）。

| 必答问题 | 明确判断 | 决定性依据 |
| --- | --- | --- |
| 证明对象是否就是指定原题？ | 是 | 目标声明与 catalog JSP-000301 的原题对应一致（见 citation.md / statement.yaml） |
| 指定 commit 是否实际验证通过？ | 是 | `lake env lean` 编译 exit 0，#print axioms 输出见下方日志 |
| 是否完整解决原题？ | 是（构造性 scoped 片段） | 证明链完整，0 sorry/admit |
| 是否满足 Lean 完整性要求？ | 满足 | `#print axioms` 仅标准三项（或无任何公理） |

Counterexample: consecutive powerful numbers 12167, 12168 (both powerful, neither a square). 0 sorry/admit.

## 固定证据

- 获取时间：2026-09-20（中国标准时间）
- 证明仓库：https://github.com/shunfeng8421/jsp301-lean
- 验证 commit：`9bc23f09dcd91731b6df194644c0ff14e323c67f`
- 源文件：`Jsp301.lean`，目标声明：`Jsp301.JSP_301`
- 工具链：leanprover/lean4:v4.34.0，mathlib v4.34.0（5ed2965…）

## 目标检查命令与结果

```bash
cd /i/research/jsp301
lake env lean Jsp301.lean   # 编译：EXIT=0，无 error
# 审计（追加 #print axioms 到副本）：
lake env lean <audit>.lean   # EXIT=0
```

`#print axioms Jsp301.JSP_301` 输出：
```
'Jsp301.JSP_301' depends on axioms: [propext, Classical.choice, Quot.sound]
```

## 证明完整性

- 0 sorry / 0 admit；无循环假设、无占位声明。
- 目标声明直接构造原题所要求的对象/反例/等值，构成 scoped 或完整证明。

## 复核层级

- 本报告为提交者自查（pre-submission self-check），依据官方 lean-verify 技能手动等价执行
  （audit.py 在 Windows 有路径兼容问题，改用 reproduction.md 规范手动审计）。
- 独立维护者复验、kernel replay 或 comparator 由官方按流程执行；本报告不替代之。
- 适用范围：仅 JSP-000301 的 Lean 证明；不决定合并、授奖或支付。
