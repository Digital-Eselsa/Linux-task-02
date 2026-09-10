# Evidence Checklist

Use this checklist while performing the lab. Capture screenshots of your own Kali Linux session. Do not use screenshots from another machine or fabricate evidence.

| ID | Task | Suggested Screenshot |
|---|---|---|
| E01 | Create `student01` | Terminal showing successful user creation/password setup |
| E02 | Switch user | `whoami` showing `student01` |
| E03 | Create `project`, `docs`, `scripts`, `bin` | Terminal showing the directory creation and/or `ls` output |
| E04 | Create `report.txt` | `cat report.txt` showing the initial report |
| E05 | View hidden files | `ls -la` inside `docs`, showing `.secret.txt` |
| E06 | Edit `report.txt` with nano | Nano showing both report lines, if permitted by your evidence requirements |
| E07 | Copy report | `ls -la ../scripts` showing `report.txt` |
| E08 | Move/rename secret file | `ls -la ../bin` showing `classified.txt` |
| E09 | Create `install.sh` | Terminal/editor showing the required script content |
| E10 | Make script executable | `ls -l install.sh` showing executable permissions |
| E11 | Remove others' read permission | `ls -l ../bin/classified.txt` showing the resulting permissions |
| E12 | Set `admin_notes.txt` to owner read/write | `ls -l admin_notes.txt` showing `-rw-------` |
| E13 | Delete `admin_notes.txt` | `ls -la docs` showing it is absent |
| E14 | Create backup | `tree project` and/or backup directory listing |
| E15 | Final verification | `tree project` plus relevant `ls -la` output |
| E16 | Bonus history | `history > commands_used.txt` and `ls -l ~/commands_used.txt` |

## Screenshot Rules
- Capture your actual terminal/session.
- Make sure the command and important output are readable.
- Avoid unnecessary personal information in screenshots.
- Use the naming convention in `screenshots/README.md`.
- One screenshot may document multiple closely related checks if the evidence is clear.
