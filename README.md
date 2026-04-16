# Liu-Uncertainty-Theory

This repository is a public mirror of the uncertainty-theory modules from
mathlib4 PR #35976. It is meant to preserve and present the PR snapshot in a
small standalone repository that is easier to browse, share, and archive than a
full mathlib4 checkout.

## Purpose

This repository is useful for:

- browsing the Uncertainty modules without cloning the full mathlib4 history;
- sharing a stable snapshot of the PR contents;
- recording which upstream PR branch commit was mirrored here.

This repository is a snapshot mirror, not a replacement for the full mathlib4
repository. If you want to run the full build or test the branch in context,
use the upstream PR branch in the source mathlib4 fork.

## Upstream Source

- Upstream PR: https://github.com/leanprover-community/mathlib4/pull/35976
- Source repository: `Phelixh/mathlib4`
- Source branch: `feat/uncertainty-pr`

## Current Mirror Status

The Lean files in this repository currently mirror the following synced source
snapshot:

- Source commit: `a8dd0ff25d659941cf289ce17320aedd82e31ae9`
- Source commit message: `docs(Uncertainty): clarify exported modules and cutoff interface`

If the upstream PR branch advances, this repository should be resynchronized and
this section should be updated to reflect the new mirrored commit.

## Repository Structure

- `Mathlib.lean`: import-all snapshot file copied from the source tree.
- `Mathlib/Uncertainty/BaseCore.lean`: core uncertainty-theory structures and
	bridge definitions.
- `Mathlib/Uncertainty/BaseDistribution.lean`: distribution-level definitions,
	interfaces, and formula-oriented constructions.
- `Mathlib/Uncertainty/BaseProcess.lean`: process-level structures, renewal
	updates, and Euler-scheme-related interfaces.
- `Mathlib/Uncertainty/Base.lean`: aggregate module importing the base
	uncertainty modules.
- `Mathlib/Uncertainty/Uncertainty.lean`: top-level public module for the
	uncertainty namespace.

## How To Sync With The PR Branch

The repository is maintained by copying the relevant Uncertainty files from the
PR branch into this mirror.

Typical workflow:

1. Update the source branch checkout of `Phelixh/mathlib4`.
2. Copy the mirrored files into this repository.
3. Review the diff.
4. Commit and push the updated snapshot.
5. Update the mirrored source commit recorded in this README.

Example PowerShell workflow:

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

## Build Note

This repository is intentionally minimal and mirrors selected files. For full
compilation against mathlib4, build the upstream PR branch repository rather
than this snapshot-only mirror.