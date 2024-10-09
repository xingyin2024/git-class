# Introduction to Git and Working with Git

## **1\. Introduction to Git**

Git is the most widely used version control system in the world. It is essential for tracking changes to code and collaborating on projects with others. In this lesson, we will cover what Git is, how it works, and how to get started using Git to manage your projects effectively.

By the end of this lesson, you will understand:

- What Git is and why it's important.
- How to install and configure Git.
- How to use basic Git commands to track and manage changes.
- How to work with Git's branching and merging functionality for collaboration.

---

## **2\. What is Git?**

Git is a distributed version control system that tracks changes in your project files. It allows multiple developers to collaborate on the same project without overwriting each other's work. Here are some key features of Git:

- **Version Control**: Git records the history of changes, allowing you to revert to previous versions of your project.
- **Collaboration**: Multiple team members can work on different parts of the project simultaneously.
- **Distributed System**: Every developer has a full copy of the repository, including its history, allowing work to continue even when offline.
- **Efficiency**: Git handles branching and merging quickly, making it highly effective for large projects.

Git enables you to manage your project's code efficiently and ensures that team members can collaborate effectively without losing any code or progress.

## **3\. Installing and Configuring Git**

To get started with Git, you need to install it on your computer. Instead of following different steps for each operating system, you can download Git directly from the official website:

1.  Go to <https://git-scm.com/downloads>.
2.  Select your operating system (Windows, macOS, Linux, or others).
3.  Follow the installation instructions provided for your specific platform.

Once installed, open a terminal (Command Prompt on Windows or Terminal on macOS/Linux) and configure Git with your name and email, which will be attached to your commits.

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

Real Example

```bash
git config --global user.name "Diego Zito"
git config --global user.email diegozito@gmail.com
```

Set your preferred text editor (e.g., Visual Studio Code) for writing commit messages:

```bash
git config --global core.editor "code --wait"
```

Finally, check your configuration to ensure everything is set up:

```bash
git config --list
```

---

## **4\. Basic Git Commands**

Understanding Git commands is essential for managing your project effectively. We'll explore each command, focusing on what it does and why it's important in your Git workflow.

For a complete list of commands covered in this lesson, refer to the `git-commands.md file`, where you’ll find examples and detailed explanations of each command we’ll use throughout the course.

If you ever need more information on a specific command, you can use `git help <command>` to display full documentation, or `git -h` for a shorter, more concise version of the command options and usage.

```bash
git help
```

or

```bash
git -h
```

Throughout this lesson, you’ll notice that many Git commands come with optional flags, like `-m` for providing a commit message, don't worry we will get into ddetails of that later.

The most important concept to understand about these flags; is that they offer additional functionality and flexibility, so be prepared to encounter and use them frequently as we dive deeper into Git's features.

---

## **5\. Git Workflow and the Staging Area**

Git follows a specific workflow to help manage changes:

1.  **Working Directory**: Where you make changes to your files.
2.  **Staging Area**: A space where changes are prepared before they are committed. You can think of it as a "draft" of changes you want to save.
3.  **Repository**: The saved history of your project, where committed changes are stored. Github would be where you store this repository online for easier version-control and collaboration.

<h1 align="center">
  <a href="">
    <img src="./assets/imgs/workflow.png" alt="Workflow">
  </a>
</h1>

The basic Git workflow looks like this:

1.  **Make Changes**: Modify files in your working directory.
2.  **Stage Changes**: Add the files you want to commit to the staging area using `git add`.
3.  **Commit Changes**: Commit your staged changes to the repository using `git commit`.

For example:

```bash
git add <filename>
git commit -m "Describe what changed"
```

The staging area gives you control over what goes into each commit, allowing you to review your changes and commit only those you are confident in.
