# Terminal Foundations

## Why This Matters

Security monitoring and incident response are terminal-heavy workflows. You need to read system state, collect evidence, and automate checks quickly and accurately.

## Command Structure

General form:

```bash
command [options] [arguments]
```

Example:

```bash
docker compose -f tooling/docker/docker-compose.yml ps
```

- `docker`: command
- `compose`: subcommand
- `-f`: option flag
- `tooling/docker/docker-compose.yml`: option value
- `ps`: operation to perform

## Exit Codes

Every command returns an exit code.

- `0`: success
- non-zero: failure

Check last command status:

```bash
echo $?
```

## Standard Streams

Each process has:

- `stdin` (0): input stream
- `stdout` (1): normal output
- `stderr` (2): error output

## Redirection and Pipes

```bash
command > file.txt
```

Send `stdout` to a file (overwrite).

```bash
command >> file.txt
```

Append `stdout` to a file.

```bash
command 2> err.txt
```

Send `stderr` to a file.

```bash
command > all.txt 2>&1
```

Send both `stdout` and `stderr` to the same file.

```bash
left_command | right_command
```

Pipe output from left command into right command input.

## Command Operators

```bash
cmd1 && cmd2
```

Run `cmd2` only if `cmd1` succeeds.

```bash
cmd1 || cmd2
```

Run `cmd2` only if `cmd1` fails.

```bash
cmd1 ; cmd2
```

Run both in sequence regardless of success.

## Variables and Substitution

Set variable:

```bash
name="kali"
```

Read variable:

```bash
echo "$name"
```

Command substitution:

```bash
now="$(date)"
echo "$now"
```

## Bash Script Safety Baseline

Use at the top of automation scripts:

```bash
set -euo pipefail
```

- `-e`: stop on command failure
- `-u`: fail on undefined variables
- `pipefail`: fail if any command in a pipeline fails

## Minimal Practice Drills

```bash
printf "ok\nerror\nok\n" | sort | uniq -c
```

```bash
(ls does-not-exist) > /tmp/out.txt 2> /tmp/err.txt
cat /tmp/err.txt
```

```bash
false; echo $?
true; echo $?
```
