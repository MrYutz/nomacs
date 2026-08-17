# Permanent delete confirmation patch

## Problem
On network drives (no trash), nomacs always shows a permanent-delete confirmation and does not allow "Remember my choice".

## Fix
This branch replaces the plain `QMessageBox` with `DkMessageBox` and sets `objectName("permanentDeleteDialog")` so the standard Remember my choice UI works.

## Apply
```bash
git apply patches/permanent-delete-remember.patch
```

Or build from this branch after restoring `ImageLounge/src/DkCore/DkUtils.cpp` from master and applying the patch.

## Note
If `DkUtils.cpp` on this branch is broken (PLACEHOLDER), reset it from master first:
```bash
git checkout master -- ImageLounge/src/DkCore/DkUtils.cpp
git apply patches/permanent-delete-remember.patch
```
