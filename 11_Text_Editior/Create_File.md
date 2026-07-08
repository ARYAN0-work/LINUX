# Creating Files from the Terminal

## 1. Using `echo`

Create a new file:
```bash
echo "line one" > myfile
```

Append to an existing file:
```bash
echo "line two" >> myfile
echo "line three" >> myfile
```

- `>` → Create/overwrite a file
- `>>` → Append text to a file

---

## 2. Using `cat` (Here Document)

Create a file with multiple lines:

```bash
cat << EOF > myfile
line one
line two
line three
EOF
```

- Useful for writing multiple lines at once.
- `EOF` marks the end of the input.