# SqlDump

Run a SELECT on your database and save the result as CSV — a Windows GUI and a command-line tool for Windows and Linux.

**Databases:** Oracle · Microsoft SQL Server · PostgreSQL · MySQL / MariaDB · IBM Db2 · SAP HANA · Sybase ASE · Informix

> **Trial version** — without a license file each dump writes at most **1,000 rows**; every other feature is available.
> Register the license file issued by DBMS Works to remove usage restrictions. See [LICENSE](LICENSE.txt).

## Download

Get the latest package from **[Releases](../../releases/latest)**.

| Package | For |
|---|---|
| `SqlDump-<version>-win-x64.zip` | Windows 10 / 11 (x64) — GUI `SqlDumpWin.exe` and CLI `SqlDump.exe` |
| `SqlDump-<version>-linux-x64.tar.gz` | Linux x64 — CLI `SqlDump` |

Self-contained: no .NET install is needed. The GUI needs the Microsoft Edge **WebView2 Runtime** (built into Windows 11).
Check the download with `SHA256SUMS.txt`.

## What it does

- Streams the result straight to the file — no row is held in memory, so large results are fine
- Delimiters of any length, including control characters (`\x1F`), quoting modes, header on/off, encodings (UTF-8, CP949, EUC-KR …)
- Line breaks inside values kept inside quotes, or replaced by marks (CR/LF Replace)
- Split by rows or by size, gzip, date placeholders in file names (`emp_{yyyyMMdd}.csv`)
- Many SQL statements in one run (`jobs` in the json config) — for schedulers, with exit codes 0 / 1 / 2
- **Loader control files** written next to the CSV from the same options: Oracle **SQL\*Loader** and **SAP HANA** `IMPORT FROM CONTROL FILE`
- Passwords in the json config are encrypted after the first successful run

## Quick start

GUI — run `SqlDumpWin.exe`, fill in the connection, press **Connect**, type the SQL, choose the output file, press **Run**.

CLI:

```
SqlDump -sample -json                      # writes a sample config
SqlDump job=SqlDump.json                   # run it
SqlDump job=SqlDump.json control=oracle "sql=SELECT * FROM emp"
```

The full manual is in the package and attached to each release: [English](../../releases/latest/download/SqlDump_manual_en.html) · [한국어](../../releases/latest/download/SqlDump_manual_kr.html).

---

## SqlDump (한국어)

DB 에서 SELECT 결과를 CSV 로 저장합니다. Windows GUI 와 CLI(Windows · Linux)가 들어 있습니다.

**지원 DB:** Oracle · SQL Server · PostgreSQL · MySQL / MariaDB · Db2 · SAP HANA · Sybase ASE · Informix

> **체험판** — 인증 파일이 없으면 덤프 한 번에 **1,000 행**까지 씁니다. 그 밖의 기능은 모두 쓸 수 있습니다.
> DBMS Works에서 발급받은 인증 파일을 등록하면 사용 제한이 해제됩니다. 사용 조건은 [LICENSE](LICENSE.txt) 를 보십시오.

- 내려받기: **[Releases](../../releases/latest)** 의 최신 묶음 (Windows x64 zip · Linux x64 tar.gz)
- .NET 설치가 필요 없습니다. GUI 는 WebView2 런타임이 필요합니다(Windows 11 에는 기본으로 있음).
- 매뉴얼(한글 · 영문)은 묶음 안과 각 릴리스의 첨부 파일에 있습니다.

© 2026 DBMS Works
