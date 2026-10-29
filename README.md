# claude-pc-signal

Lets Claude restart the Claude desktop app on Winter's PC when the device
connection has dropped and the PC can't be reached directly.

- `restart.txt` holds one UTC timestamp. A scheduled task on the PC
  ("Claude Restart Watchdog", `tools\claude-restart\Claude-Watchdog.ps1` in the
  CK3 Modding folder) reads it every 2 minutes. When the value changes, the PC
  fully quits and reopens Claude, then writes `Reopened <time>` to
  `tools\claude-restart\last_reopened.txt`.
- To request a restart, commit a new timestamp to `restart.txt` on `main`.
- The repo is public so the PC needs no credentials. It holds only timestamps.
