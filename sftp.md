## Transferring Files via SFTP to Great Lakes

To securely transfer files between your local machine and the **Great Lakes** cluster, use `sftp`:

```bash
sftp yourusername@greatlakes.arc-ts.umich.edu
```

Replace `yourusername` with your UMich username.

### Common `sftp` Commands

- `cd <remote-path>` — Change directory on the **remote** system.
- `lcd <local-path>` — Change directory on your **local** machine.
- `pwd` — Show current **remote** directory.
- `lpwd` — Show current **local** directory.
- `ls` — List files in the **remote** directory.
- `lls` — List files in the **local** directory.
- `get <filename>` — Download a file **from remote to local**.
- `put <filename>` — Upload a file **from local to remote**.

### Example

```bash
sftp yourusername@greatlakes.arc-ts.umich.edu
cd projects/my_project
lcd ~/Downloads
put script.py
get results.txt
exit
```

This is a simple and secure way to move files without needing a full graphical interface or file browser.

