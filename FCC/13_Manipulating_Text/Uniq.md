# `uniq` Command

Filters out consecutive duplicate lines from sorted input.

## Syntax

```bash
uniq <filename>
```

## Common Usage

| Command | Description |
|---------|-------------|
| `uniq file` | Remove consecutive duplicate lines. |
| `sort file1 file2 \| uniq > file3` | Combine, sort, remove duplicates, and save the result to `file3`. |
| `uniq -c file` | Count occurrences of consecutive duplicate lines. |
| `uniq -d file` | Display only duplicate lines. |

# `split` Command

Splits a large file into smaller files.

## Syntax

```bash
split [OPTIONS] <file>
```

## Common Usage

| Command | Description |
|---------|-------------|
| `split <file>` | Split a file into smaller files (1000 lines each by default). |
| `split -l 500 <file>` | Split into files with 500 lines each. |
| `split -b 10M <file>` | Split into files of 10 MB each. |
| `split -d <file>` | Use numeric suffixes instead of letters. |
| `wc -l <file>` | Count the number of lines in a file. |

## Example

```bash
wc -l american-english
# 99171 american-english

split american-english
```

Creates multiple smaller files, each containing **1000 lines** by default.

---

# `join` Command

Joins two files based on a common field.

## Syntax

```bash
join <file1> <file2>
```

## Common Usage

| Command | Description |
|---------|-------------|
| `join file1 file2` | Join two sorted files on the first field. |
| `join -1 2 -2 1 file1 file2` | Join using different fields from each file. |
| `join -t "," file1.csv file2.csv` | Use a custom delimiter. |

> **Note:** Both input files must be **sorted** on the join field before using `join`.