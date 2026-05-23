---
"@open-codesign/desktop": patch
---

Harden the workspace files watcher: fall back to polling for any filesystem watch error (previously only EPERM / EACCES / EISDIR), explicitly covering EINVAL, ENOSPC, and ERR_FEATURE_UNAVAILABLE_ON_PLATFORM that surface on Windows UNC paths, full disks, and Bun runtimes. Unknown FS errors now degrade gracefully instead of breaking the Files panel. (#352)
