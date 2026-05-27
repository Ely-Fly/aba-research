# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Running the app

```bash
./run-pomodoro.sh
```

The script prefers Homebrew Python 3.12 (e.g. `/opt/homebrew/opt/python@3.12/bin/python3.12`) over macOS system Python to avoid a Tk 8.5 rendering bug where `Label` widgets often don't paint. It falls back to system Python if none is found.

To run directly with a specific interpreter:

```bash
TK_SILENCE_DEPRECATION=1 /opt/homebrew/opt/python@3.12/bin/python3.12 pomodoro.py
```

## Architecture

Single-file app (`pomodoro.py`) — one class `PomodoroApp` wraps all state and UI.

**Threading model**: The countdown runs in a daemon thread (`_tick`). All UI mutations go through `root.after(0, ...)` to marshal back onto the Tk main thread. The `is_running` flag is the only cross-thread signal; no locks are needed because Tk is single-threaded and the flag is only ever set to `False` from the main thread.

**macOS Tk workaround**: macOS system Tk 8.5 often fails to render `Label` widgets. To stay compatible, the app renders all text display elements (clock, mode label, progress bar, dots, count) using `tk.Button` styled like labels (`relief="flat"`, `borderwidth=0`, `highlightthickness=0`, `cursor="arrow"`). Do not replace these with `Label` widgets unless you also require running on Homebrew Python/Tk.

**Progress display**: Uses a Unicode text bar (`_progress_bar`) with `█`/`░` characters instead of a Canvas arc, for the same macOS compatibility reason.

**Notifications**: Fired via `osascript` subprocess; no pyobjc dependency required.
