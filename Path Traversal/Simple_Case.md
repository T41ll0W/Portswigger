# Path Traversal Exploitation

This section focuses on exploiting a **Path Traversal** vulnerability by manipulating the `$_GET` variable (`'filename'`) in the URL. Path Traversal occurs when an application does not properly sanitize user input, allowing attackers to access files outside the intended directory.

## How It Works
- The attacker injects directory traversal sequences, such as `../../../../../../etc/passwd`, into the `filename` parameter.
- These sequences navigate the server's filesystem, enabling access to sensitive files (e.g., `/etc/passwd` on Unix-based systems).
- The number of `../` sequences does not need to be exact. Even if you use more than necessary (e.g., 10), the system will still resolve the path correctly.

### Example
Given a vulnerable URL:
```
http://example.com/images/filename=../../../../../../directory

```

## Lab: File path traversal, simple case :

This lab contains a path traversal vulnerability in the display of product images.

To solve the lab, retrieve the contents of the /etc/passwd file.




