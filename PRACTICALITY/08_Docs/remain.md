Linux Documentation — What You Need
1. man ⭐⭐⭐

Main Linux documentation tool.

man ls
man cp
man mkdir

Inside man:

/word → search
n     → next result
q     → quit
2. --help ⭐⭐⭐

Quick help for a command.

ls --help
cp --help

Use this when you just need to remember options.

3. help ⭐⭐

For Bash built-in commands:

help cd
help echo
4. info 🟡

More detailed documentation, especially for GNU software.

info bash

You don't need to study its navigation.

5. /usr/share/doc/ 🟡

Package-specific documentation.

ls /usr/share/doc/

Just know it exists.

man Sections — Only Remember This

You don't need to memorize all 8 sections.

Just know:

1 → normal user commands
2 → system calls
3 → library functions
5 → configuration files
8 → system administration commands

For example:

man 5 passwd
🧠 The Actual Skill

Don't think:

"I need to memorize every Linux command."

Think:

Need something
     ↓
Know / guess the command
     ↓
man command
     ↓
Read options
     ↓
Use it

Or for quick help:

command --help
Final priority

🟢 Master: man, --help, help
🟡 Know: info, /usr/share/doc/
🔴 Skip: detailed Info navigation, desktop help systems, memorizing every man section.

Section 08 → ✅ Done.