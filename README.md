# 📦 upack

**upack** is a lightweight, zero-dependency CLI tool designed for developers to aggregate their project context into a single Markdown file. It’s the perfect companion for sharing code with LLMs (like ChatGPT, Claude, or Gemini) for analysis, debugging, or architectural reviews.

## ✨ Key Features

- **Native Core**: Written in pure Go. It doesn't require Git or any external binaries to scan your project.
- **Smart Filtering**: Automatically excludes hidden files (starting with `.`), binary data, and heavy dependency folders (`node_modules`, `venv`, `dist`, etc.).
- **Ignore Support**: Respects rules from both `.gitignore` and `packignore` files.
- **Zero Configuration**: Just run it in your project root, and you're good to go.
- **Cross-Platform**: Single-binary execution for Windows, Linux, and macOS.

## 🚀 Installation & Quick Start

### Windows
1. Download `upack.exe` from [Releases](https://github.com/rbirukoff-rgb/upack/releases).
2. Place it in a folder included in your `PATH` (e.g., `C:\bin`).
3. Open your terminal in a project folder and run:
   ```powershell
   upack
   ```

> [!IMPORTANT]
> **Troubleshooting: "Blocked by Device Guard"**
> If you see an error stating that `upack.exe` is blocked by your organization's policy, you can bypass this using **WSL (Windows Subsystem for Linux)**:
> 1. Download `upack_linux`.
> 2. Move it to the WSL internal filesystem:
>    ```bash
>    mkdir -p ~/bin
>    cp /mnt/c/path/to/download/upack_linux ~/bin/
>    chmod +x ~/bin/upack_linux
>    ```
> 3. Create a `upack.bat` file in your Windows `PATH` (e.g., `C:\bin\upack.bat`) with the following content:
>    ```batch
>    @echo off
>    wsl ~/bin/upack_linux %*
>    ```
> Now you can run `upack` normally in Windows CMD/PowerShell.

### Linux / macOS
1. Download the appropriate binary (`upack_linux` or `upack_mac`).
2. Make the file executable:
   ```bash
   chmod +x upack_linux  # or upack_mac
   ```
3. (Optional) Move it to `/usr/local/bin` for global access:
   ```bash
   sudo mv upack_linux /usr/local/bin/upack
   ```
4. Run the command:
   ```bash
   upack
   ```

## 📂 What's in the Report?

The utility generates a `context_[folder_name].md` file containing:
1. **Project Tree**: A visual representation of your project structure.
2. **File Contents**: All text-based source code, wrapped in Markdown code blocks with proper syntax highlighting.

## 🛠 File Ignoring Logic

The tool automatically skips:
- All hidden files and directories (starting with `.`).
- Binary files (images, executables, fonts, etc.).
- Standard build artifacts and dependency folders.

You can add custom rules to a `packignore` file in your project root (using standard `.gitignore` syntax).

---
Developed by **Roman Birukoff**.  
*Good practice in the 21st century.*
