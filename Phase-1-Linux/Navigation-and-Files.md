# Day 1 - Linux Basic Commands (Navigation & File Basics)

**Date:** Monday, March 23, 2026
**Time Spent:** 1 hour
**Platform:** Linux Terminal (Ubuntu)

## Commands Learned:

### 1. User & Location Information
- **whoami** - Shows current username
- **pwd** - Print working directory (shows where you are currently)

### 2. Navigation
- **ls** - List files and directories in current location and you can also check files in specific file as well by writting full path
- **cd** - Change directory
  - `cd Desktop` - Go to Desktop folder
  - `cd ~` - Go to home directory
  - `cd -` - Go to previous directory in which you were before moving into the current one

### 3. File Creation & Viewing
- **touch** - Create empty file and update the timestamp of the file or files
  - Example: `touch testing1.txt`, `touch testing1.txt testing2.txt`
- **nano** - Text editor to create/edit files
  - Save: `Ctrl + S`, Exit: `Ctrl + X`
- **cat** - Display file contents and also work to show files content merged
  - `cat filename` - Show file
  - `cat -b filename` - Number non-empty lines
  - `cat -n filename` - Number all lines
- **less** - View file page by page
  - `less -b filename`
- **file** - Check file type
  - Example: `file testing1.txt`

### 4. Help & History
- **history** - Shows all previously used commands

## Practical Work Done:

✅ Found current username with `whoami`
✅ Checked current location with `pwd`
✅ Navigated to Desktop folder
✅ Created file: `testing1.txt`
✅ Edited file using nano editor
✅ Viewed file using cat and less
✅ Checked file type
✅ Navigated back to home with `cd ~`
✅ Used `cd -` to toggle between directories

## Key Learnings:

- Linux is case-sensitive
- `~` is shortcut for home directory
- `cd -` toggles between current and previous directory
- `cat` shows entire file, `less` shows page by page
- `cat -n` adds line numbers

## Status:
✅ Day 1 Completed - Basic navigation & file viewing mastered!
