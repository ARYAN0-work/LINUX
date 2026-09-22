df -Th / — IMPORTANT ✅

You should understand:

df -Th /
df → disk/filesystem usage
-T → show filesystem type
-h → human-readable
ext4 → common Linux filesystem
/ → check the filesystem mounted at root

This is genuinely useful when you're troubleshooting a Linux server:

“Is the disk getting full?”

/proc/swaps — LOW PRIORITY 🟡

You only need to know:

Swap = disk space used as overflow when RAM is under pressure.

And:

cat /proc/swaps

shows active swap areas.

That's enough for now.