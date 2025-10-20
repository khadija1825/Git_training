Good question 👍

You're expecting your **terminal prompt** to show the current Git branch name (like `(main)`), but by default it doesn’t always do that — it depends on your **bash prompt configuration**.

Here’s how to fix it 👇

---

## 🧭 Option 1: Quick Check (just to verify the branch)

You can always check which branch you’re on manually with:

```bash
git branch
```

You’ll see something like:

```
* main
```

The asterisk `*` marks your current branch.

---

## 🖥️ Option 2: Show the branch name in your terminal prompt automatically

If you want your terminal to **always display the branch name**, you can enable **Git branch info in your Bash prompt**.

### Step 1: Edit your Bash configuration file

Open the file:

```bash
nano ~/.bashrc
```

### Step 2: Add this line at the bottom:

```bash
export PS1="\u@\h:\w\[\033[32m\]\$(__git_ps1 ' (%s)')\[\033[00m\]\$ "
```

This tells your shell to show the branch name (in green) at the end of the prompt, like:

```
khadija@Khadija:~/Git_training (main)$
```

### Step 3: Load the changes:

```bash
source ~/.bashrc
```

---

## 🧩 Note:

If you see an error like `__git_ps1: command not found`, it means Git’s prompt helper isn’t loaded yet.

To fix that:

1. Make sure this line is also in your `~/.bashrc` (above the `PS1` line):

   ```bash
   source /usr/share/git/completion/git-prompt.sh
   ```
2. Then re-run:

   ```bash
   source ~/.bashrc
   ```

---

✅ **Result:**
Your prompt will now look like:

```
khadija@Khadija:~/Git_training (main)$
```

…and the `(main)` will update automatically whenever you switch branches.

---

Would you like me to give you a version that works specifically for **Ubuntu on WSL** (which most people use for Git training)?
