# Q&A Revision
- Question 1

Q: Why would you normally use:

- sudo apt install nginx => instead of manually downloading a .deb and using dpkg?

Your answer:

"because it will find exactly that package and run it"

🟡 What you got right

You understood that apt finds the package for you.

❌ What was missing

The major advantage is dependency management.

````bash
APT can find:

nginx
 ↓
dependencies
 ↓
download them
 ↓
install everything

So the better answer:

APT finds the package from repositories and handles downloading and dependencies automatically, while dpkg mainly handles the specific .deb package you're giving it.

````

Question 2

- Q: Ubuntu server. Which would you use?

sudo apt install nginx

or

sudo dnf install nginx
Your answer:

"2nd one because we want to install a package"

❌ Why you were wrong

Both commands install packages.

The important question wasn't:

"Do we want to install a package?"

````bash
It was:

"Which Linux distribution are we using?"

We said Ubuntu.

Therefore:

Ubuntu
 ↓
Debian family
 ↓
apt

So:

sudo apt install nginx
Compare:
Ubuntu / Debian
     ↓
    apt
RHEL / Fedora
     ↓
    dnf
🔑 Lesson

Don't choose a package manager based on what you're trying to do.

Choose it based on the Linux distribution/family.

````

Question 3

- Q: What does sudo mean?

sudo apt install nginx
Your answer:

"it some sort of permission"

🟢 Correct!

You correctly recognized that it is related to permissions.

More specifically:

sudo allows a permitted user to execute a command with superuser/root privileges.

normal user
     ↓
   sudo
     ↓
root privileges

Question 4

- Q: Why does:

mkdir myproject

usually work without sudo, while:

sudo apt install nginx

usually needs elevated privileges?

Your answer:

"because for that you are making a folder and for second one you are modifying the whole system"

🟢 Correct concept!

Your reasoning was right.

More precisely:

mkdir myproject
 ↓
Creates a directory where your user
has permission
 ↓
No sudo required

Whereas:

apt install nginx
 ↓
Installs software into protected
system locations
 ↓
Requires elevated privileges
🔑 Important lesson

Linux permissions depend on what you're trying to access/modify and where.

Question 5

Q: Difference between:

sudo dpkg -i nginx.deb

and:

sudo apt install nginx
Your answer:

"first only installs second one will take care of the whole system"

🟡 Almost correct

Your basic idea was right:

dpkg
 ↓
Specific .deb package
apt
 ↓
Higher-level package management
❌ Small correction

APT does not "take care of the whole system."

It manages packages.

So the better wording is:

dpkg directly works with a .deb package, while apt manages the broader package installation process, including finding packages in repositories and resolving dependencies.

🔥 The 30-Second Revision

If you forget everything, remember this:

                 Linux
                   │
              Linux Kernel
                   │
                Debian
                   │
                Ubuntu
                   │
              Linux Mint

For Ubuntu:

Ubuntu
 ↓
Debian family
 ↓
.deb
 ↓
apt
 ↓
dpkg
Package management
apt
 ↓
High-level
 ↓
Find + download + dependencies + install
dpkg
 ↓
Low-level
 ↓
Directly handles .deb packages
Permissions
sudo
 ↓
Run command with elevated/root privileges
Most important DevOps lesson

When you see a Linux server:

First identify the distribution/family.

Because that affects things like:

Package manager
Package format
Commands
Configuration
Administration

And since we're using Ubuntu WSL, this is the ecosystem we'll actually practice:

apt
dpkg
bash
sudo