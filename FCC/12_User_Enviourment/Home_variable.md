# Home Variable

The **`HOME`** environment variable stores the path to the current user's home directory. Commands like `cd` use this variable by default.

| Command | Explanation |
|---------|-------------|
| ```bash<br>echo $HOME<br>cd /bin<br>``` | Display the value of `$HOME`, then change to the `/bin` directory. |
| ```bash<br>pwd<br>``` | Shows the current working directory (`/bin`). |
| ```bash<br>cd<br>``` | Running `cd` without any arguments automatically returns to your home directory (`$HOME`). |
| ```bash<br>pwd<br>``` | Confirms that you are back in your home directory (e.g., `/home/me`). |

### Example

```bash
echo $HOME
# /home/me

cd /bin
pwd
# /bin

cd
pwd
# /home/me
```

> **Note:** `cd` and `cd $HOME` are equivalent—they both take you to your home directory.