# Agent Notes

This project is built and tested inside a Windows environment, so assume Windows-first behavior and double-check any assumptions.

- Use backslash `\\` when documenting or scripting paths (e.g., `C:\\Users\\5600X2\\...`); mixing `/` and `\\` tends to confuse the IAR + batch tooling.
- Preserve CRLF line endings and UTF-8 encoding; several IDE integrations choke if you silently flip files to LF.
- Treat the filesystem as case-insensitive and avoid creating files that differ only by case.
- Many build steps rely on PowerShell/batch helpers; prefer Windows-native tooling unless you have verified a cross-platform path.
- Quote long paths (they usually live under `C:\\Users\\...`) and keep MAX_PATH limits in mind when adding deeply nested folders.
- Do not assume Unix-only features (symlinks, /tmp, chmod flags, shebangs) exist; provide the Windows-friendly alternative.
- Coding, building, and compiling stay inside VS Code or CLion via the Makefile targets; only use EWARM to launch debug/run sessions so build artifacts stay reproducible.
- The toolchain is pinned to `C:\\iar\\ewarm-9.70.1\\arm\\bin`; point PATH/Makefile variables there before invoking `make`.

When in doubt, reproduce your changes from a clean PowerShell session on Windows before sending a PR.
