# Day 2 - Linux File Operations & Directory Management

**Date:** Tuesday, March 24, 2026
**Time Spent:** 1 hour
**Platform:** Linux Terminal (Local Machine)

## Commands Learned:

### 1. File Operations
- **cp** - Copy files
  - Syntax: `cp source destination`
  - Example: `cp testing1.txt /home/husnain/Documents`
  - Copies file from one location to another

- **mv** - Move or rename files
  - `mv -i` - Interactive mode (asks before overwrite)
  - `mv oldname.txt newname.txt` - Rename file
  - `mv file.txt /path/to/folder/` - Move file to different location
  - Example: `mv testing1.txt test.txt` (renamed)

### 2. Directory Management
- **mkdir** - Create directory/folder
  - `mkdir foldername` - Create single folder
  - `mkdir -p parent/child` - Create nested folders at once
  - Example: `mkdir -p nano/test` (created nano folder with test subfolder)

### 3. File & Directory Deletion
- **rm** - Remove/delete files and folders
  - `rm filename` - Delete a file
  - `rm -r foldername` - Delete folder with all contents (recursive)
  - ⚠️ **DANGER:** No undo! Deleted files are gone forever!
  - Example: `rm -r nano` (deleted entire nano folder)

### 4. Getting Help
- **whatis** - Shows one-line description of any command
  - Example: `whatis nano`, `whatis more`, `whatis less`
  - Useful to quickly understand what a command does

## Practical Work Done:

✅ Copied `testing1.txt` from Desktop to Documents folder
✅ Navigated to Documents and verified file was copied
✅ Moved file back to Desktop using `mv -i`
✅ Renamed file from `testing1.txt` to `test.txt`
✅ Created nested folders: `nano/test/`
✅ Moved `test.txt` into the nested folder using combined command
✅ Navigated into nested folders using `cd`
✅ Deleted entire `nano` directory with all contents
✅ Used `whatis` to learn about different commands

## Advanced Technique Used:

**Command Chaining with `&&`:**
```bash
mkdir -p nano/test && mv test.txt /home/husnain/Desktop/nano/test
```
- `&&` means "do this AND then do that"
- First creates folders, then moves file
- Second command only runs if first succeeds

## Key Learnings:

- `cp` creates a copy (original stays)
- `mv` moves/renames (original is gone from old location)
- `mkdir -p` creates all parent folders automatically
- `rm -r` is VERY powerful - deletes everything inside folder
- Always double-check before using `rm -r`!
- Can chain multiple commands with `&&`

## Mistakes & Corrections:

❌ Tried: `cd .. ..` (wrong syntax)
✅ Fixed: `cd ..` (goes up one level)

❌ Tried: `rm nano` (can't remove directory this way)
✅ Fixed: `rm -r nano` (need -r flag for directories)

❌ Typo: `what is nano` (space in command)
✅ Fixed: `whatis nano` (no space)

## Commands Used (Day 2): 14-46 from history

## Status:
✅ Day 2 Completed - File operations & directory management mastered!
