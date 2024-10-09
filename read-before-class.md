# Read Before Class

## Setting Up Visual Studio Code for Git

This file includes instructions on how to set up Visual Studio Code (VS Code) for the Git class by enabling the `code .` command on both Mac and Windows. It serves as a precursor to the class, ensuring that students are ready to follow along with the examples and exercises in the Git class.

## Topics Covered:

1.  Installing the `code .` command for VS Code on Mac and Windows.
2.  Why this setup is important for Git usage.
3.  Configuring Git for proper line-ending management across different operating systems.

---

## 1\. **Installing the `code .` Command for VS Code**

To make working with VS Code easier, we need to enable the `code .` command, which allows you to open VS Code directly from the terminal.

##### **On Mac**:

To enable this on Mac, follow these steps:

1.  Open VS Code.
2.  Press `Cmd+Shift+P` to open the Command Palette.
3.  Type `Shell Command: Install 'code' command in PATH` and press `Enter`.
4.  Close and reopen your terminal for the changes to take effect.

This allows you to simply type `code .` in your terminal to open the current folder in VS Code, making it easier to work with Git.

##### **On Windows**:

To enable this on Windows:

1.  Open VS Code.
2.  Go to `File` > `Preferences` > `Settings`.
3.  In the search bar, type `code path` and ensure that the "Add to PATH" option is checked.
4.  Restart your terminal or command prompt.

Once set up, you can type `code .` to open the current folder in VS Code, making it easier to work with Git repositories directly.

---

### 2\. **Why This Is Important for Git Usage**

Having the `code .` command enabled allows you to quickly open and manage your Git repository from VS Code with just one terminal command. This speeds up your workflow, especially when switching between the terminal and the editor during Git operations. Throughout the Git class, you will be using the terminal to perform Git operations and open project folders in VS Code using this command.

---

### 3\. **Configuring Git for Proper Line Endings**

Another important setup step for both Windows and Mac/Linux users is configuring Git to handle line endings correctly. This ensures that files are consistent across different operating systems, preventing potential issues when collaborating with others.

#### **For Windows Users:**

You need to configure Git to automatically handle line endings between Windows (CRLF) and Unix-based systems (LF):

- **What**: Configures Git to automatically handle line-ending conversions between Windows (CRLF) and Unix-based systems (LF).
- **Why**: This prevents issues when collaborators are using different operating systems. On Windows, Git converts LF to CRLF when checking out files and converts back when committing.

To set this up, type the following in your terminal:

```bash
git config --global core.autocrlf true
```

#### **For Mac/Linux Users:**

On Unix-based systems (Mac/Linux), the configuration only converts line endings when committing:

- **What**: Configures Git to convert line endings only when committing (not when checking out), keeping the line endings as-is on Unix-based systems.
- **Why**: This prevents line-ending conflicts while still allowing Windows users to handle them correctly.

To set this up, type the following in your terminal:

```bash
git config --global core.autocrlf input
```

---

## **Additional Information**

These Git configuration commands are important and will help you avoid line-ending issues when working with teams on different operating systems. For future reference, these commands and more will be available in the `git-commands.md` file as part of this class.

Make sure these steps are completed before the class so you can follow along smoothly!
