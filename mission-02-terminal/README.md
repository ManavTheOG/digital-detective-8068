# Mission 2 - Become Comfortable with the Terminal

## 1. Task / objective
Practice core command-line navigation and file management inside a safe sandbox folder, understand command flags and pipes, and inspect a package manager.

## 2. Work completed
* Executed directory navigation, file creation, copying, moving, and inspection commands directly in Terminal.
* Created `terminal-practice/` using `mkdir`, initialized `notes.txt` with `touch`, tested overwriting (`>`) vs. appending (`>>`), and created `notes-backup.txt`.
* Compared standard `ls` output against `ls -lah` and piped `ls -l` into `head -n 5`.
* Checked package manager availability safely without installing or removing software.

## 3. Commands / tools used
* `pwd`, `ls`, `ls -l`, `ls -lah`, `cd ..`, `mkdir`, `touch`, `cp`, `mv`, `cat`, `head` — Core POSIX file and directory utilities.
* `|` (Pipe operator) — Redirects standard output of one command into standard input of the next.
* `brew --version` & `brew list` — Checked Homebrew installation status and viewed the list of managed packages (when installed).

## 4. My understanding
### Task 2.1 — Basic Terminal Operations
| Operation / command name | What it does | What I observed |
| :--- | :--- | :--- |
| Current-directory display (`pwd`) | Prints the full absolute path of the current working directory. | Displayed `/Users/[redacted]/Developer/S_AI/digital-detective-8068` |
| Directory listing (`ls`) | Lists visible files and folders in the current directory. | Listed 11 items including `evidence mission-00-setup mission-01-computer-basics mission-02-terminal`. |
| Detailed listing (`ls -l`) | Displays permissions, owner, file size in bytes, and modification date. | Returned 12 lines including the `total` header and item metadata. |
| Change directory (`cd ..`) | Moves the shell session up one level to the parent directory. | `pwd` changed to `/Users/[redacted]/Developer/S_AI` before returning to `digital-detective-8068`. |
| Create directory (`mkdir`) | Creates a new empty folder at the specified path. | Created `terminal-practice` without errors. |
| Create empty file (`touch`) | Creates a zero-byte file or updates its timestamp if it exists. | Created `terminal-practice/notes.txt` with initial size 0 bytes. |
| Copy file (`cp`) | Duplicates a file to a new path while keeping the original intact. | Copied `notes.txt` to `notes-copy.txt` with both present. |
| Move / rename file (`mv`) | Moves a file to a new directory or renames it in place. | Renamed `notes-copy.txt` to `notes-backup.txt`. |
| Display file contents (`cat`) | Reads a file and prints its text contents directly to the terminal. | Printed 2 lines: `First line of practice notes. Second line appended safely.` |

### Task 2.2 — Safe File Practice Questions
* **Replacing vs. adding text:** Using `>` truncates (overwrites) the file before writing new text, whereas `>>` appends new text to the end of the file while preserving existing lines.
* **Copying vs. moving a file:** `cp` creates an independent duplicate leaving the source file untouched; `mv` relocates or renames the original file so only one copy remains.
* **Current-directory display (`pwd`):** Shows your exact location in the directory tree from the root (`/`), preventing accidental edits in the wrong folder.
* **Why directory listing (`ls`) is useful:** Lets you immediately verify file names, folder structure, hidden files, and permissions directly from the keyboard.

### Task 2.3 — Flags and Pipes
* **Flags (`ls` vs. `ls -lah`):** Plain `ls` showed 11 visible entries. Running `ls -lah` produced 16 lines because `-a` revealed hidden entries (`.`, `..`, `.git`), `-l` added metadata columns, and `-h` formatted sizes into human-readable units.
* **Pipes (`ls -l | head -n 5`):** The pipe symbol (`|`) sends the standard output (`stdout`) of `ls -l` into the standard input (`stdin`) of `head -n 5`, filtering the output to only the first 5 lines:

```text
total 8
drwxr-xr-x  3 [redacted]  staff    96 27 Nov 22:50 evidence
drwxr-xr-x  3 [redacted]  staff    96 27 Nov 22:50 mission-00-setup
drwxr-xr-x  3 [redacted]  staff    96 27 Nov 22:50 mission-01-computer-basics
drwxr-xr-x  3 [redacted]  staff    96 27 Nov 22:50 mission-02-terminal
```

### Task 2.4 — Package Managers
Package managers (such as Homebrew on macOS or `apt` on Ubuntu) automate downloading, verifying, installing, updating, and removing command-line tools and libraries from trusted repositories. Homebrew is installed (`Homebrew 7.0.12`). Managed packages viewed via `brew list`: `ada-url, aom, brotli, btop, c-ares, ca-certificates, cairo, dav1d, ffmpeg, fmt, fontconfig, freetype, fribidi, gcc, gettext, gh, giflib, glib, gmp, graphite2, harfbuzz, hdrhistogram_c, htop, icu4c@78, isl, jpeg-turbo, json-c, lame, libavif, libffi, libimagequant, libmpc, libnghttp2, libnghttp3, libngtcp2, libomp, libpng, libraqm, libtiff, libunistring, libuv, libvmaf, libvpx, libx11, libxau, libxcb, libxdmcp, libxext, libxrender, little-cms2, llhttp, lz4, lzo, merve, mpdecimal, mpfr, mpg123, nbytes, ncurses, node, numpy, openblas, openjpeg, openssl@3, openssl@4, opus, pcre2, pillow, pipx, pixman, python-matplotlib, python@3.14, qhull, readline, sdl2-compat, sdl3, simdjson, simdutf, sqlite, svt-av1, tree, uvwasi, webp, x264, x265, xorgproto, xz, zstd, ollama-app`.

## 5. Difficulties faced
No major difficulties.

## 6. How I resolved them
Not applicable.

## 7. Evidence / files
* `mission-02-terminal/README.md`
* `terminal-practice/notes.txt`
* `terminal-practice/notes-backup.txt`
* `evidence/safe-outputs.txt`

## 8. Commit details
* **Commit message:** `Complete Terminal and file management mission`
* **Status:** Committed and pushed to GitHub on `main`.
