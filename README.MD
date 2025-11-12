# Combine Files Script

## Overview

This Bash script combines the contents of all files with specified extensions in the current directory (and its subdirectories) into one single text file. It is designed to be run from **Git Bash** on Windows.

The script:

- Asks you which file extensions to include (for example: `jsx`, `css`).
- Recursively collects all matching files.
- Skips the `node_modules` directory.
- Writes each file's **relative path**, followed by its **contents**, separated by blank lines.
- Saves everything into a file named after the current directory and chosen extensions, like: `contents-of-lv3capstone-jsx-css.txt`

---

## Example Output

If your project structure looks like this:

    src/App.jsx
    src/App.css
    src/components/Navbar.jsx
    src/components/Navbar.css

and you choose the extensions `jsx` and `css`, the generated file will look like:

    src/App.jsx

    ...App.jsx contents...


    src/App.css

    ...App.css contents...


    src/components/Navbar.jsx

    ...Navbar.jsx contents...


    src/components/Navbar.css

    ...Navbar.css contents...

---

## Installation and Setup

1.  Save the script as:

        C:\Users\Administrator\combine-files.sh

2.  Open **Git Bash** and make it executable:

    ```bash
    chmod +x ~/combine-files.sh
    ```

3.  Add your home directory to your `PATH` (if not already):

    ```bash
    echo 'export PATH="$HOME:$PATH"' >> ~/.bashrc
    source ~/.bashrc
    ```

4.  You can now run the script from anywhere with:

    ```bash
    combine-files.sh
    ```

---

## Usage

1.  Navigate to your project folder in Git Bash:

    ```bash
    cd /c/path/to/your/project
    ```

2.  Run the script:

    ```bash
    combine-files.sh
    ```

3.  Enter extensions when prompted (without the dot):

    ```bash
    Extension to include (or '-' for no more): jsx
    Extension to include (or '-' for no more): css
    Extension to include (or '-' for no more): -
    ```

4.  The script will collect matching files (excluding `node_modules`) and create an output file like:

        contents-of-myproject-jsx-css.txt

---

## Features

- Recursively processes files in the current directory.
- Automatically skips the `node_modules` folder.
- Uses clear formatting between files.
- Automatically names the output file based on the current directory and selected extensions.
- Safe and idempotent: existing output file is replaced safely.

---

## Example Run

```bash
$ cd /c/Users/Administrator/projects/lv3-capstone
$ combine-files.sh
This script will combine file contents from the current directory (recursively).
Enter extensions to include (without the dot). Type '-' when finished.
Extension to include (or '-' for no more): jsx
Extension to include (or '-' for no more): css
Extension to include (or '-' for no more): -
Collecting files (excluding node_modules)...
Done. Wrote: contents-of-lv3capstone-jsx-css.txt
```

---

## License

This script is provided freely for personal and educational use.
