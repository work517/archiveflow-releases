# ArchiveFlow — releases

**ArchiveFlow** lets your AI assistant look inside archives safely: summarize ZIP / 7z / RAR / TAR files without extracting them, rate their safety, search and read files, extract them safely, and repair garbled Korean / Japanese / Chinese / Russian file names.

This repository only hosts **installable releases**. The source code is not public.

## Install (Claude Desktop, Windows)

1. Download the latest `archiveflow-<version>.mcpb` from [Releases](../../releases).
2. Double-click it, or drag it into Claude Desktop → Settings → Extensions.
3. Choose the folders ArchiveFlow may access (default: Downloads) and whether it is read-only.

Then ask Claude, for example: *"What's inside Downloads/report.zip? Is it safe to open?"*

## What it does

| Tool | |
|---|---|
| `inspect_archive` | Summary without extracting + safety rating (safe / caution / danger) |
| `scan_security` | Path traversal, links, zip bombs, disguised programs, macros; deep mode finds prompt-injection text and personal data |
| `list_entries` · `search_archive` · `read_entry` | Browse, search names and text, read one file (text is marked as untrusted) |
| `extract_archive` | Safe extraction: unsafe entries are always blocked, nothing is overwritten, plan first |
| `fix_zip_names` | Rewrite garbled legacy file names (CP949, Shift-JIS, GBK, CP866/1251) as UTF-8 |
| `create_archive` · `diff_archives` · `test_archive` · `engine_info` | Create without secrets, compare, verify |

- Everything runs **locally** on your PC. Files are never uploaded.
- Access is limited to the folders you choose. Passwords never appear on a command line.
- Two independent checks for ZIPs (the engine's view and the names actually stored in the file), nested archives up to two levels, overlapping-entry zip bombs, and a size watchdog during extraction.
- Safety benchmark: 28 crafted malicious or tricky archives — 28/28 flagged, 0 files written outside the target folder.

## 한국어

**ArchiveFlow**는 AI 비서가 압축 파일을 안전하게 다루게 해 줍니다. 풀지 않고 요약·안전 판정, 검색·읽기, 안전하게 풀기, 깨진 한글·일본어·중국어 파일명 복구.

설치: [Releases](../../releases)에서 `archiveflow-<버전>.mcpb`를 받아 더블클릭(또는 Claude Desktop → 설정 → 확장 프로그램에 끌어다 놓기) → 허용 폴더 선택.
모든 처리는 내 PC에서만 하며, 파일은 어디에도 올라가지 않습니다. 이 저장소에는 설치 파일만 있고 소스 코드는 공개하지 않습니다.

## License

ArchiveFlow is proprietary software — see [LICENSE.txt](LICENSE.txt).
Third-party components (including 7-Zip, LGPL) are listed in `THIRD_PARTY_NOTICES.txt` inside each `.mcpb`.
