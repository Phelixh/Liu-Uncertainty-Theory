# Liu-Uncertainty-Theory

中文 | English

## 中文说明

### 项目简介

本仓库是 mathlib4 PR #35976 中 Uncertainty Theory 相关模块的公开镜像，目的是将该 PR 的核心代码以更轻量、便于浏览和分享的形式独立保存下来。

它适合用于：

- 快速查看不确定理论相关 Lean 模块，而不必克隆完整的 mathlib4 历史；
- 对外展示当前 PR 快照；
- 记录此镜像仓库对应的上游 PR 分支提交版本。

本仓库是镜像快照，不是完整的 mathlib4 替代品。如果要在完整上下文中编译、测试或继续开发，请使用上游 PR 分支所在的 mathlib4 仓库。

### 上游来源

- Upstream PR: https://github.com/leanprover-community/mathlib4/pull/35976
- Source repository: `Phelixh/mathlib4`
- Source branch: `feat/uncertainty-pr`

### 当前镜像状态

本仓库当前代码对应的上游 PR 快照为：

- Source commit: `5621a1c81ff9c6b1ab25afe12af40ba67180054e`
- Source commit message: `fix(Uncertainty): align normal inverse and demote examples`

仓库中的镜像代码文件已经与上述上游提交保持一致。如果 PR 分支后续继续推进，则需要再次同步代码并更新本 README 中记录的提交信息。

### 仓库结构

- `Mathlib.lean`：从源仓库复制的 import-all 快照文件。
- `Mathlib/Uncertainty/BaseCore.lean`：不确定理论核心结构与桥接定义。
- `Mathlib/Uncertainty/BaseDistribution.lean`：分布层定义、接口与公式化构造。
- `Mathlib/Uncertainty/BaseProcess.lean`：过程层结构、renewal update 与 Euler scheme 相关接口。
- `Mathlib/Uncertainty/Base.lean`：基础模块聚合入口。
- `Mathlib/Uncertainty/Uncertainty.lean`：不确定理论命名空间的顶层公开模块。

### 如何与 PR 分支同步

同步方式是将上游 PR 分支中的目标文件复制到本仓库，并记录新的上游提交号。

典型流程：

1. 更新 `Phelixh/mathlib4` 中的 `feat/uncertainty-pr` 分支。
2. 将镜像文件复制到本仓库。
3. 检查差异。
4. 提交并推送新的镜像快照。
5. 更新本 README 中记录的 source commit。

示例 PowerShell 流程：

```powershell
Set-Location E:\Academic\66\uncertainty20260329\pr35976-fix
git checkout feat/uncertainty-pr
git pull --ff-only origin feat/uncertainty-pr

Set-Location E:\Academic\66\uncertainty20260329\Lius-Uncertainty-Theory
Copy-Item ..\pr35976-fix\Mathlib.lean .\Mathlib.lean -Force
Copy-Item ..\pr35976-fix\Mathlib\Uncertainty\Base.lean .\Mathlib\Uncertainty\Base.lean -Force
Copy-Item ..\pr35976-fix\Mathlib\Uncertainty\BaseCore.lean .\Mathlib\Uncertainty\BaseCore.lean -Force
Copy-Item ..\pr35976-fix\Mathlib\Uncertainty\BaseDistribution.lean .\Mathlib\Uncertainty\BaseDistribution.lean -Force
Copy-Item ..\pr35976-fix\Mathlib\Uncertainty\BaseProcess.lean .\Mathlib\Uncertainty\BaseProcess.lean -Force
Copy-Item ..\pr35976-fix\Mathlib\Uncertainty\Uncertainty.lean .\Mathlib\Uncertainty\Uncertainty.lean -Force

git status
git add Mathlib.lean Mathlib/Uncertainty/*.lean README.md
git commit -m "sync: update snapshot from mathlib4 PR #35976"
git push origin main
```

### 构建说明

本仓库刻意保持精简，只镜像选定文件。若要在完整 mathlib4 环境中编译，请到上游 PR 分支仓库中执行构建，而不是在这个快照镜像仓库中直接尝试完整编译。

## English

### Overview

This repository is a public mirror of the Uncertainty Theory modules from mathlib4 PR #35976. Its purpose is to preserve and present the core PR contents in a smaller standalone repository that is easier to browse, share, and archive than a full mathlib4 checkout.

It is useful for:

- browsing the Uncertainty modules without cloning the full mathlib4 history;
- sharing the current PR snapshot publicly;
- recording which upstream PR branch commit is mirrored here.

This repository is a snapshot mirror, not a replacement for the full mathlib4 repository. If you want to build, test, or continue development in context, use the upstream mathlib4 PR branch.

### Upstream Source

- Upstream PR: https://github.com/leanprover-community/mathlib4/pull/35976
- Source repository: `Phelixh/mathlib4`
- Source branch: `feat/uncertainty-pr`

### Current Mirror Status

The code in this repository currently mirrors the following upstream PR snapshot:

- Source commit: `5621a1c81ff9c6b1ab25afe12af40ba67180054e`
- Source commit message: `fix(Uncertainty): align normal inverse and demote examples`

The mirrored code files in this repository are aligned with that upstream commit. If the PR branch moves forward, this repository should be resynchronized and this README should be updated accordingly.

### Repository Structure

- `Mathlib.lean`: import-all snapshot file copied from the source tree.
- `Mathlib/Uncertainty/BaseCore.lean`: core uncertainty-theory structures and bridge definitions.
- `Mathlib/Uncertainty/BaseDistribution.lean`: distribution-level definitions, interfaces, and formula-oriented constructions.
- `Mathlib/Uncertainty/BaseProcess.lean`: process-level structures, renewal updates, and Euler-scheme-related interfaces.
- `Mathlib/Uncertainty/Base.lean`: aggregate entry module for the base uncertainty modules.
- `Mathlib/Uncertainty/Uncertainty.lean`: top-level public module for the uncertainty namespace.

### How To Sync With The PR Branch

This mirror is maintained by copying the target files from the upstream PR branch into this repository and then recording the new upstream commit in the README.

Typical workflow:

1. Update the `feat/uncertainty-pr` branch in `Phelixh/mathlib4`.
2. Copy the mirrored files into this repository.
3. Review the diff.
4. Commit and push the refreshed snapshot.
5. Update the source commit recorded in this README.

The PowerShell example above can be used as the standard sync procedure.

### Build Note

This repository is intentionally minimal and mirrors only selected files. For full compilation against mathlib4, build the upstream PR branch repository instead of this snapshot-only mirror.