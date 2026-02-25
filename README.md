# notes

A lightweight, terminal-based note-taking application powered by Bash script. It features Markdown integration and AI-powered cheat sheet generation via Gemini.

## Features

* **Terminal-Centric**: Capture your ideas, snippets, and commands instantly without leaving the command line.
* **Markdown Support**: Render beautiful notes using `mdcat`.
* **Gemini AI Integration**: Automatically generate command cheat sheets if they don't exist in your notes.
* **Clipboard Integration**: Extract and copy code blocks from specific sections directly to your clipboard.
* **Simple Navigation**: Search by titles, view specific sections, or manage multiple note files easily.

## Requirements

* **Primary Editor**: `nvim` (default) or `vim`.
* **Rendering**: `mdcat` (for markdown preview).
* **AI Features**: `gemini` CLI tool and Google Cloud SDK (`gcloud`) authenticated via `gcloud auth application-default login`.
* **Clipboard**: `pbcopy` (macOS) or `xclip` (Linux).

## Installation

1. Save the script as `notes`.
2. Give it execution permissions: `chmod +x notes`.
3. Move it to your PATH (e.g., `/usr/local/bin/`).
4. Set your notes directory in the script:
```bash
MY_NOTES_DIR="$HOME/Documents/google_share/notes"

```



## Usage

### Commands Overview

| Option | Description |
| --- | --- |
| `-h` | Display help message. |
| `-c FILE` | Create a new note file (e.g., `notes -c work`). |
| `-o NAME` | Switch to/open a specific note file. |
| `-f` | List all available `.md` files in the notes directory. |
| `-e` | Edit the current note file using Neovim. |
| `-a` | Append text from standard input (End with `Ctrl+D`). |
| `-md` | Display the current note with Markdown formatting. |
| `-raw` | Display the raw content of the note file. |
| `-t` | List all titles in the current note. |
| `-t N` | Display the content of the N-th title. |
| `-t N --code` | Copy the code block from the N-th title to clipboard. |
| `-s STR` | Search for a specific string within titles. |
| `-g CMD` | Generate a cheat sheet for `CMD` using Gemini AI. |
| `-d N` | Delete `N` lines from the bottom of the file. |

### AI Cheat Sheet Generation

The `-g` option is particularly powerful. It checks if the command already exists in your notes. If not, it calls Gemini to generate a structured cheat sheet:

```bash
notes -g "docker-compose"

```

Use `--force` to generate it even if the keyword exists.

## Note Format

To ensure the search and display functions work correctly, keep your notes in the following Markdown format. Each section must start with a `# ` (H1) or `### ` (as per your script's grep logic):

```markdown
# Replace String Pattern in All Files
Use sed to replace text recursively.
```bash
find . -type f -exec sed -i 's/abcd/efgh/g' {} +

```

# Check Directory Sizes

```bash
du -sh ./* | sort -hr

```

```

## Environment
- **Tested on**: macOS (Silicon/Intel).
- **Shell**: Bash / Zsh.

## License
MIT License. Feel free to fork and modify it to suit your workflow!

```
