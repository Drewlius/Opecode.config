---
name: sudoAskPass
description: Use whenever a command needs root/sudo. Run `pkexec --user root <command> <arguments>`.
---

# Elevated commands

Run exactly one command as root:

    pkexec --user root <command> [args...]

A single password dialog appears for the $USER. PAM verifies the
password. It never goes to stdout, a pipe, or a helper process.

## Equivalent wrapper:

    /home/slippy/.config/opencode/skills/sudoAskPass/scripts/sudoaskpass.sh <command> [args...]

## Hard rules

1. NEVER ask the user to paste their password into chat.
2. NEVER run plain interactive `sudo`; it has no tty here.
3. Announce that the polkit dialog is about to pop up before running the command.
