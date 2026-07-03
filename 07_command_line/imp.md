One more thing

Notice the difference between these prompts:

Regular user:

aryan@LAPTOP-JKAF7PUH:~$

Root user:

root@LAPTOP-JKAF7PUH:~#
$ → Normal user.
# → Root (administrator).

Whenever you see #, be extra careful. As root, commands like:

rm -rf /

or even accidentally deleting the wrong directory can damage the system because root bypasses normal permission checks.