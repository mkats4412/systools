# notes - terminal base note app using bash script.

- this works with vim
- put your idea for terminal
- note usage on terminal
- very simple
- note should be following
each titles should start with '###'.. and you can write anything freely.
the following is just sample  
```text
### Replace String Pattern in All Files in a Directory

$ find . -type f -exec sed -i 's/abcd/efgh/g' {} +

### Preview Markdown in VSCode
	•	command+shift+V: Same pane
	•	command+k v: Side-by-side pane

### grep Command Options
	•	grep -i "string": Search ignoring case
	•	grep -A 3: Show 3 lines after each match

### Location of skhd Configuration File for Shortcut Keys

/Users/user/.config/skhd/skhdrc

### About pipx (Python-based Applications)
	•	pipx list: Lists currently installed applications

### gtts-cli (Python Program)

gtts-cli 'hello' --output hello.mp3

### Resolving Command Line Errors After Installing VS Code

codesign --force --deep --sign - /Applications/Visual\ Studio\ Code.app

### List Globally Installed Packages with npm

npm list -g

### Update Packages with npm
	•	npm update <package-name>
	•	npm up <package-name>
	•	npm update <package@version>

### Troubleshooting Sleep Issues

sudo rm /Library/Preferences/com.apple.PowerManagement.*

### Remove Files from Tracking After Setting .gitignore

cache-clean = !git rm --cached `git ls-files -ci --exclude-standard`

### Check Directory Sizes

du -sh ./* | sort -hr

### Check External Disk Temperature

smartctl -a /dev/disk4

### Command to Move Home Folder

sudo rsync -avh --progress ~/ <destination User folder>

### .gitignore Example

*.swp
._*
.DS_Store
node_modules
InfoScraper-darwin-x64
release
.sass-cache
```  


tested only on macos
License: MIT

# And this is how to use
```
print_help() {
    echo "Usage: notes [-c FILE_NAME] [-d N] [-e] [-h] [-i] [-l] [-o NOTE_NAME]"
    echo "Options:"
    echo " -c FILE_NAME  Create a new note file with the specified name"
    echo " -d N          Delete N lines from the bottom"
    echo " -e            Edit the notes file using Vim"
    echo " -h            Display this help message"
    echo " -a            Append note and end with ^D"
    echo " -v            list md files in the notes directory"
    echo " -f            Display the contents of the notes file"
    echo " -o NOTE_NAME  Open the note with the specified name (without .md extension)"
    echo " -s CONTENTS   Search contents from title"
    echo " -t CONTENTS   Display titles matching the given CONTENTS"
    echo " -t            Display all titles"
    echo " -t N          Display the Nth title with its content"
    echo " w/o           Show the current notes file"
}
```

