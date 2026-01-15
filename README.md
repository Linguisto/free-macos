# free (macOS)

Linux-like `free(1)` memory summary for macOS.

A small Python utility that implements the GNU `free` command for macOS. It provides a familiar interface to check memory and swap usage.

## Features

- **GNU-compatible output**: Similar table format to the original `free` command.
- **Human-readable**: Use the `-h` flag to show units (default).
- **Multiple units**: Supports bytes (`-b`), kibibytes (`-k`), mebibytes (`-m`), and gibibytes (`-g`).
- **Continuous monitoring**: Use `-s` (seconds) and `-c` (count) to watch memory usage over time.
- **macOS specific details**: Use `--details` to see macOS-specific memory breakdown (wired, compressed, active, inactive, etc.).

## Installation

Install with `homebrew`:

```bash
brew tap Linguisto/free
brew install free
```

Alternatively, download the `free` script, make it executable, and move it to your path:

```bash
chmod +x ./free
sudo mv ./free /usr/local/bin/
```

## Usage

```bash
# Basic usage (defaults to human-readable)
free

# Show totals and human-readable units
free -h -t

# Repeat every 2 seconds for 5 times
free -s 2 -c 5

# Show macOS specific memory breakdown
free --details
```

## Options

```text
  -h          human-readable output
  --help      show this help message and exit
  --version   show version and exit
  -b          show output in bytes
  -k          show output in kibibytes
  -m          show output in mebibytes
  -g          show output in gibibytes
  -w          wide output (accepted for GNU free compatibility)
  -t          display a line with totals
  -s SECONDS  repeat printing every N seconds
  -c COUNT    repeat count with -s, 0 means forever
  --details   show additional macOS breakdown
```

> Note: Values are approximations based on macOS memory accounting and may differ
> from Linux `free` output.
