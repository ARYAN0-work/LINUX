# `curl` Command

`curl` (Client URL) is a command-line tool used to **transfer data** to or from a server using URLs. It supports protocols such as HTTP, HTTPS, FTP, and many others.

---

# Basic Syntax

```bash
curl [options] URL
```

---

# Common Commands

### Display a web page

```bash
curl https://example.com
```

Displays the HTML content in the terminal.

---

### Save a web page to a file

```bash
curl -o saved.html https://example.com
```

- `-o` → Save output with the specified filename.

---

### Download using the original filename

```bash
curl -O https://example.com/file.zip
```

- `-O` → Saves the file using its original name.

---

### Follow redirects

```bash
curl -L https://example.com
```

- `-L` → Automatically follows HTTP redirects.

---

### Show only HTTP headers

```bash
curl -I https://example.com
```

Displays only the response headers.

---

### Send JSON data (POST request)

```bash
curl -X POST \
-H "Content-Type: application/json" \
-d '{"name":"Aryan"}' \
https://example.com/api
```

---

# Common Options

| Option | Purpose |
|---------|---------|
| `-o file` | Save output to a specific file |
| `-O` | Save using original filename |
| `-L` | Follow redirects |
| `-I` | Fetch only HTTP headers |
| `-X` | Specify HTTP method |
| `-H` | Add HTTP headers |
| `-d` | Send request data |

---

# Common Uses

- Download web pages and files
- Test REST APIs
- Send GET, POST, PUT, DELETE requests
- Check HTTP response headers
- Debug web services

---

# Summary

- `curl` transfers data using URLs.
- Supports many internet protocols.
- Commonly used for API testing, downloading files, and web debugging.
```