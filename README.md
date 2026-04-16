# Liu-Uncertainty-Theory

A public scholarly mirror of the Uncertainty Theory modules developed in mathlib4 PR #35976.  
mathlib4 PR #35976 中 Uncertainty Theory 模块的公开学术镜像。

## About / 项目说明

This repository is maintained as a public-facing archival mirror of selected Lean sources from the Uncertainty Theory development in mathlib4 PR #35976. Its purpose is to provide a stable, citation-friendly, and lightweight presentation of the mirrored snapshot for scholarly reference, public dissemination, and provenance tracking.

本仓库作为 mathlib4 PR #35976 中不确定理论相关 Lean 源文件的公开存档镜像进行维护，其目标是为学术引用、对外展示与版本留档提供一个更稳定、便于引用且更轻量的快照载体。

This repository is not the canonical development repository and should not be treated as a replacement for a full mathlib4 checkout. For full in-context compilation, integration, and ongoing development, use the upstream PR branch.

本仓库不是规范意义上的开发主仓库，也不替代完整的 mathlib4 工作树。如需在完整上下文中编译、联调或继续开发，请使用上游 PR 分支所在的 mathlib4 仓库。

## Upstream Source / 上游来源

- Upstream PR: https://github.com/leanprover-community/mathlib4/pull/35976
- Source repository: `Phelixh/mathlib4`
- Source branch: `feat/uncertainty-pr`

## Current Mirrored State / 当前镜像状态

- Mirrored source commit: `3f9f9f7af495242fcd38ec08fb67512a28c02fd4`
- Source commit message: `Merge branch 'master' into feat/uncertainty-pr`
- Snapshot role: public mirror and presentation layer for the selected Uncertainty files

The mirrored file set currently agrees with the selected Uncertainty files on the current PR head.

当前镜像文件集与当前 PR head 中对应的不确定理论文件保持一致。

## Citation / 引用建议

If this mirror repository is cited in an article, lecture note, talk, or project documentation, it is best described as a public mirror of the Uncertainty Theory modules from mathlib4 PR #35976, together with the mirrored source commit recorded above.

如果需要在论文、讲义、报告或项目文档中引用本仓库，建议将其表述为 mathlib4 PR #35976 中 Uncertainty Theory 模块的公开镜像，并同时注明本 README 中记录的镜像 source commit。

Recommended BibTeX:

```bibtex
@misc{gao2026liuuncertaintytheory,
	author       = {Fei Gao},
	title        = {Liu's Uncertainty Theory},
	year         = {2026},
	howpublished = {\url{https://github.com/Phelixh/Liu-Uncertainty-Theory}},
	note         = {Public mirror of the Uncertainty Theory modules from mathlib4 PR \#35976; mirrored source commit 3f9f9f7af495242fcd38ec08fb67512a28c02fd4; accessed 2026-04-16}
}
```

## References / 参考文献

1. Liu, B. (2026). *Uncertainty Theory* (5th ed.). Uncertainty Theory Laboratory. Retrieved from https://cloud.tsinghua.edu.cn/d/df71e9ec330e49e59c9c/
2. Liu, B. (2015). *Uncertainty Theory* (4th ed.). Springer Berlin, Heidelberg. https://doi.org/10.1007/978-3-662-44354-5
3. leanprover-community. *mathlib4 pull request #35976*. https://github.com/leanprover-community/mathlib4/pull/35976

## Mirrored Contents / 镜像内容

- `Mathlib.lean`: import snapshot file copied from the source tree / 从源仓库复制的 import 快照文件
- `Mathlib/Uncertainty/BaseCore.lean`: core structures and bridge definitions / 核心结构与桥接定义
- `Mathlib/Uncertainty/BaseDistribution.lean`: distribution-side interfaces and formula layers / 分布层接口与公式化结构
- `Mathlib/Uncertainty/BaseProcess.lean`: process structures, renewal updates, and Euler-scheme interfaces / 过程结构、renewal update 与 Euler scheme 接口
- `Mathlib/Uncertainty/Base.lean`: aggregate entry module for the base uncertainty modules / 基础模块聚合入口
- `Mathlib/Uncertainty/Uncertainty.lean`: top-level public module for the uncertainty namespace / 不确定理论命名空间顶层公开模块

## Synchronization Workflow / 同步流程

This mirror is synchronized by updating the upstream PR checkout, copying the selected files into this repository, reviewing the resulting diff, and then refreshing the recorded source commit in the repository metadata.

本镜像通过以下方式同步：更新上游 PR 分支 checkout，将选定文件复制到本仓库，检查差异，然后刷新仓库元数据中记录的 source commit。

Typical maintenance steps:

1. Update `Phelixh/mathlib4` on `feat/uncertainty-pr`.
2. Copy the mirrored files into this repository.
3. Review the diff and refresh the recorded source commit.
4. Commit and push the updated snapshot to `main`.

## Build Note / 构建说明

This repository intentionally mirrors only a curated subset of files. For full compilation against mathlib4, build the upstream PR branch repository rather than this snapshot-only mirror.

本仓库只镜像一个经过筛选的文件子集。若要在完整 mathlib4 环境中编译，请直接构建上游 PR 分支仓库，而不是在这个快照镜像仓库中进行完整构建。