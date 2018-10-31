# Git Hooks

---

## What?
Allows for scripts to be run during steps in the Git workflow eg. before a commit

---

## Why?
- To enforce standards
- To execute repetitive tasks

---

## Client-side hooks
Executed before or after git operations

...

### Examples
- Disallow commits with lint/test errors
- Enforce a commit message format
- Configure environment/dependencies after clone/checkout
- Remove executable permission from code files

---

## Server-side hooks
Executed before or after a push is received

...

### Examples
- Reject a push if user does not have the proper permissions
- Send out notifications
- Inform user of pull request process
- Deploy to a server

---

## How?
- A hook is an executable script
- Hooks stored in `.git/hooks`
- Samples for each available hook included by default
- Hooks are __not__ copied when you clone a repository
  - Use external tool/process to copy hooks

```
.git
├── HEAD
├── config
├── description
├── hooks
│   ├── applypatch-msg.sample
│   ├── commit-msg.sample
│   ├── post-update.sample
│   ├── pre-applypatch.sample
│   ├── pre-commit.sample
│   ├── pre-push.sample
│   ├── pre-rebase.sample
│   ├── pre-receive.sample
│   ├── prepare-commit-msg.sample
│   └── update.sample
├── info
├── objects
└── refs
```

...

- Hooks are named as per sample files without the extension
  - `pre-commit.sample` => `pre-commit`
- Must be executable
  ```
  chmod +x pre-commit
  ```

...

- Hooks can be written in any language as long as the correct interpreter is chosen
- Non-zero exit code indicates failure
  - Will prevent completion of the Git operation in pre hooks

```
#!/bin/sh
echo "[pre-commit hook (shell)] Commit blocked"
exit 1
```

```
#!/usr/bin/env node
console.log('[pre-commit hook (node)] Commit blocked');
process.exit(1);
```

---

## Demo

---

# Fin
