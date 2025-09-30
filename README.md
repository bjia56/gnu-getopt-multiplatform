# gnu-getopt-multiplatform
Multiplatform builds of GNU getopt. Powered by [Cosmopolitan Libc](https://github.com/jart/cosmopolitan) and the [Chimp](https://github.com/bjia56/chimp) file format.

## Runtime Dependencies

This getopt build is packaged as a Chimp polyglot script that works across platforms with minimal dependencies:

### Windows
- `cmd.exe` (Windows Command Processor)
- `powershell.exe` (for version checking and base64 decoding fallback)

The downloaded artifact must be renamed to `getopt.cmd` to be run from a Windows shell. Alternatively, run it
with Bash on Windows.

### Unix/Linux/macOS
- Bourne shell (`/bin/sh`)
- Core utilities: `uname`, `dd`, `chmod`, `exec`, `mkdir`, `tail`, `expr`, `exit`
- Base64 decoder (tries in order):
  1. `base64` command
  2. `gbase64` command (GNU base64)
  3. `openssl` (excludes LibreSSL and MidnightBSD variants)
  4. `python3` (versions 3.13, 3.12, 3.11, 3.10, 3.9)
