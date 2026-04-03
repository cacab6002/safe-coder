# 🛡️ safe-coder - Safer AI coding for projects

[![Download / Install](https://img.shields.io/badge/Download-Visit%20GitHub%20Page-blue?style=for-the-badge)](https://github.com/cacab6002/safe-coder)

## 🚀 What this is

Safe Coder is a setup package for the `pi` coding agent. It adds safety checks before the agent runs risky commands or changes files outside your project folder.

Use it when you want an AI coding tool to stay inside the workspace and ask before it does anything risky.

## 🖥️ Windows setup

### 1. Open the download page

Go to the GitHub page here:

https://github.com/cacab6002/safe-coder

### 2. Install the `pi` coding agent

Open PowerShell and run:

```powershell
npm install -g @mariozechner/pi-coding-agent
```

If Windows asks for permission, allow it.

### 3. Install Safe Coder

Run this command in PowerShell:

```powershell
pi install npm:safe-coder
```

This adds Safe Coder to your `pi` setup.

### 4. Start using it

Open the `pi` coding agent and point it at your project.

Safe Coder loads its guardrails and project extensions on its own.

## 📦 What you need

- Windows 10 or Windows 11
- Internet access
- Node.js installed on your PC
- Permission to install tools on your system

## 🔧 What Safe Coder does

### 🧱 Blocks risky shell commands

Safe Coder checks shell commands before they run. It can stop commands like:

- `rm -rf`
- `sudo`
- `chmod 777`
- `chown 777`

If a command looks unsafe, it asks for clear approval first.

### 📁 Keeps changes inside your project

Safe Coder checks file actions like:

- reading files
- writing files
- editing files

It blocks access when a path points outside your current project folder.

### 🧩 Loads project-specific extensions

Safe Coder works like a package you add to `pi`. It can load extra skills and extensions that fit your project.

That helps the agent follow your project rules without extra setup.

## 🪟 Simple install steps for Windows

### Step 1: Install Node.js

If Node.js is not on your computer, install it first.

Use the current LTS version from the official Node.js site.

After install, close and reopen PowerShell.

### Step 2: Check that Node.js works

Run:

```powershell
node -v
npm -v
```

If both commands show version numbers, you are ready.

### Step 3: Install the agent

Run:

```powershell
npm install -g @mariozechner/pi-coding-agent
```

### Step 4: Install Safe Coder

Run:

```powershell
pi install npm:safe-coder
```

### Step 5: Open your project

Start `pi` in the folder where your project lives.

Safe Coder will use that folder as the workspace boundary.

## 🧭 How to use it day to day

1. Open PowerShell.
2. Move to your project folder.
3. Start the `pi` coding agent.
4. Let Safe Coder handle the safety checks.

If the agent tries to run a risky command, review it before you allow it.

If the agent tries to touch files outside the project, block it and keep the work inside the folder you chose.

## ✅ Good use cases

Safe Coder is useful for:

- school projects
- small apps
- team codebases
- test projects
- AI-assisted editing in a folder you trust

It helps reduce mistakes when an AI tool works with your files.

## 🧪 Example of what it may block

A command like this may need approval:

```bash
rm -rf node_modules
```

A file edit like this may get blocked:

```text
C:\Users\YourName\Desktop\secret-file.txt
```

A safe path inside your project folder should work as expected.

## 🗂️ Project layout

You do not need to manage the package files by hand, but the package is built to plug into `pi` and load:

- guardrails
- workspace checks
- extra skills
- project rules

## 🔒 Safety behavior

Safe Coder focuses on two main controls:

- command safety
- file boundary checks

These checks help keep the agent from doing work that goes beyond your intent.

## 🛠️ Common tasks

### Install the package again

If you need to reinstall Safe Coder, run:

```powershell
pi install npm:safe-coder
```

### Update the agent

Use the normal `npm` update flow for `pi` if you want the latest version of the coding agent.

### Remove the package

If you no longer want Safe Coder, remove it through your `pi` setup in the way your agent package manager expects.

## 💬 When the agent asks for approval

If you see a request for a command like:

- remove files
- change system settings
- change file permissions
- use admin access

pause and read it first.

Only allow it if you know what it will do.

## 🔍 Troubleshooting

### `npm` is not recognized

Install Node.js, then reopen PowerShell.

### `pi` is not recognized

Install `@mariozechner/pi-coding-agent` again and check that global npm tools are on your PATH.

### Safe Coder does not seem active

Make sure you ran:

```powershell
pi install npm:safe-coder
```

Then start `pi` from the project folder again.

### Commands are still blocked

This can happen when a command matches a safety rule.

Review the command and use a safer version if possible.

## 📥 Download and install

Use this page to get started:

https://github.com/cacab6002/safe-coder

Open the page, follow the install steps for Windows, then add Safe Coder to your `pi` setup with:

```powershell
pi install npm:safe-coder
```

## 🧾 Quick start

```powershell
npm install -g @mariozechner/pi-coding-agent
pi install npm:safe-coder
```

After that, open your project folder and start using `pi` with Safe Coder enabled