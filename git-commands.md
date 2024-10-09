## **4\. Basic Git Commands**

This file serves as a comprehensive reference for the Git commands covered during the lesson. Each command is listed with an explanation of its purpose, usage, and any relevant flags or options to enhance your understanding of Git's functionality. As you work through the course, use this file as a guide to reinforce the commands you're learning and to practice them on your own projects.

By familiarizing yourself with these commands, you’ll be able to manage your version control workflow efficiently and gain deeper insights into Git's powerful capabilities.

### **4.0 - `git help`**

- **What**: Displays the manual page for a specific Git command, showing its options, usage, and detailed descriptions.
- **Why**: This is a valuable resource when you need to quickly reference how a command works or learn more about its flags. It helps clarify any questions you might have about the functionality of Git commands, making it a handy tool for both beginners and advanced users.

```bash
git help
```

- **Example**: To get help with the `commit` command:

```bash
git help commit
```

For a more concise, summary version of the command options, you can use the shorthand version:

```bash
git <command> -h
```

For example:

```bash
git commit -h
```

---

---

### **4.1 - `git init`**

- **What**: Initializes a new, empty Git repository in the current directory.
- **Why**: This is the first step in turning a regular directory into a Git-tracked project. It creates a `.git` folder that stores all the version control data.

```bash
git init
```

#### What happens after you input this command on your terminal (pointing to the correct folder you want to initizialize a git repository)

##### Let's look at this image:

<h1 align="center">
  <a href="">
    <img src="./assets/imgs/git-init.png" alt="Git Init example terminal">
  </a>
</h1>

Branch Creation: When you run git init, Git automatically creates a default branch.

Historically, this branch has been named master. However, you can set a different default branch name, such as main, using a configuration setting (explained below).

```bash
git branch -m main
```

This command renames the current branch (usually master) to main, allowing you to update branch names after initialization.

**Important**

- **For future reference, the command `git config --global init.defaultBranch main` ensures that whenever you initialize a new Git repository using `git init`, the default branch will be named `main` instead of the traditional `master`, aligning your workflow with modern conventions or any naming standard you prefer across all your projects.**

```bash
git config --global init.defaultBranch main
```

- **This command retrieves and displays the current default branch name configuration, confirming if main has been set.**

```bash
git config --global init.defaultBranch main
```

After you run the command `git config --global init.defaultBranch main` on your terminal; everytime you create a new git-repository on your local folder this is what you will see after running the command `git init` on your terminal.

<h1 align="center">
  <a href="">
    <img src="./assets/imgs/git-init-setup-global.png" alt="Git Init example terminal">
  </a>
</h1>

---

### **4.2 - `git status`**

- **What**: Shows the status of your working directory and the staging area, letting you know which files are modified, untracked, or staged for commit.
- **Why**: This command gives you a snapshot of the current state of your project, helping you understand what changes are ready to commit and what still needs attention.

```bash
git status
```

---

### **4.3 - `git status -s`**

- **What**: Shows the status of your working directory and staging area in a short, compact format.
- **Why**: This is useful when you want a quicker, cleaner view of your changes without the more verbose output of `git status`.

```bash
git status -s
```

---

### **4.4 - `git add`**

- **What**: Stages changes for the next commit. This command tells Git to include changes in the staging area, preparing them for a commit.
- **Why**: The `git add` command gives you control over which changes to include in the next commit. You can choose to add specific files, groups of files based on patterns, or all changes at once.

#### **Ways to Use `git add`:**

1.  ##### **Adding a Specific File**\

    You can stage individual files by specifying the filename.

    **Example**:

    ```bash
    git add <filename>
    ```

    This adds just the specified file to the staging area. For example:

    ```bash
    git add index.html
    ```

    or

    ```bash
    git add README.md
    ```

2.  ##### **Adding All Changes at Once**\

    To stage all the changes in your current directory, you can use the `.` flag. This adds all modified and untracked files to the staging area.

    **Example**:

    ```bash
    git add .
    ```

3.  ##### **Adding Files with a Specific Extension**

    You can also add all files of a certain type by specifying a file extension. This is helpful when working with multiple files of the same type (e.g., all text files or markdown files).

    **Example (Adding all `.md` files)**:

    ```bash
    git add *.md
    ```

    This adds all `markdown` files in the current directory to the staging area.

---

### **4.5 - `git commit`**

- **What**: Records the changes from the staging area to the repository, saving a snapshot of your project's current state.
- **Why**: Commits act as checkpoints in your project. They help you track progress, revert to previous states, and explain the context of the changes using a commit message.

Example (with a message):

    git commit -m "Commit message"

---

### **4.6 - `git log`**

- **What**: Displays the commit history, showing a list of past commits in reverse chronological order.
- **Why**: Use this command to review the history of your project, including details like who made changes, when they were made, and what the commit message was.

```bash
git log
```

---

### **4.7 - `git log --oneline`**

- **What**: A condensed version of `git log`, showing only one line per commit (including a shortened hash and commit message).
- **Why**: This is helpful when you want a quick overview of the commit history without all the extra details.

```bash
git log --oneline
```

---

### **4.8 - `git diff`**

- **What**: Shows the differences between various states of your project (working directory vs. staging area, or staging area vs. last commit).
- **Why**: This command allows you to compare changes before staging or committing them, ensuring that you know exactly what has been modified.

Example (compare working directory and staging area):

```bash
git diff
```

---

### **4.9 - `git ls-files`**

- **What**: Lists the files that Git is tracking.
- **Why**: This command helps you verify which files are currently being tracked by Git, providing insight into the content of your repository.

```bash
git ls-files
```

---

### **4.10 - `git rm --cached` -r <filename>**

- **What**: Removes a file or folder from the staging area without deleting it from the working directory.
- **Why**: Use this command when you mistakenly add a file or folder to Git and want to stop tracking it without removing it from your project.

Example (removing a file from Git's index):

```bash
git rm --cached <filename>
```

Example (removing a folder recursively):

```bash
git rm --cached -r <foldername>
```

---

### **4.11 - `git config --global core.autocrlf true` - (Windows)**

- **What**: Configures Git to automatically handle line ending conversions between Windows (CRLF) and Unix-based systems (LF).
- **Why**: This prevents issues when collaborators are using different operating systems. On Windows, Git converts LF to CRLF when checking out files and converts back when committing.

```bash
git config --global core.autocrlf true
```

---

### **4.12 - `git config --global core.autocrlf input` - (Mac/Linux)**

- **What**: Configures Git to convert line endings only when committing (not when checking out), keeping the line endings as-is on Unix-based systems.
- **Why**: This prevents line-ending conflicts while still allowing Windows users to handle them correctly.

```bash
git config --global core.autocrlf input
```

### **4.13 - Removing Git from a Folder Locally**

- **What**: This command removes Git tracking from the current folder, effectively "un-initializing" the Git repository.
- **Why**: If you want to stop version controlling a folder but keep the folder and its contents intact, removing the `.git` folder will achieve this.

```bash
rm -rf .git
```

- **Summary**: This command deletes the hidden `.git` directory, which stores all Git version control data (commits, branches, etc.). The folder itself and its files remain untouched, but the folder will no longer be tracked by Git.

---

#### **Why Are These Commands Important?**

- **Tracking Changes**: `git status`, `git add`, and `git commit` allow you to see what's happening in your project and record important changes.
- **Understanding History**: `git log` and `git diff` help you see past changes and ensure you are on the right track.
- **Managing Files**: `git rm`, `git ls-files`, and the autocrlf configuration commands give you control over what Git tracks and how it handles different file types and line endings across operating systems.
