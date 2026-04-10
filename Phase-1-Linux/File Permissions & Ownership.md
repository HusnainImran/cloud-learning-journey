# Day 3 - File Permissions & Ownership

**Date:** Thursday, April 09, 2026
**Time Spent:** 1 hour
**Platform:** Linux Terminal - XAMPP Installation & Configuration

## What I Learned:

### File Permission Basics:
- **r** = read (4)
- **w** = write (2) 
- **x** = execute (1)

### Permission Groups:
- **User (u)** - File owner
- **Group (g)** - Group members
- **Others (o)** - Everyone else

### Permission Numbers Explained:
- **777** = rwxrwxrwx (everyone can do everything)
- **751** = rwxr-x--x (owner: all, group: read+execute, others: execute only)
- **761** = rwxrw---x (owner: all, group: read+write, others: execute only)

## Real-World Task Completed:

### Installing XAMPP on Linux
✅ Downloaded XAMPP installer file
✅ Made installer executable with `chmod u+x`
✅ Ran installer with `sudo`
✅ Navigated to XAMPP installation directory `/opt/lampp/`
✅ Modified permissions on `htdocs/testing` folder

## Commands Practiced:

### 1. Navigation & Inspection
```bash
ls -l                    # Check file permissions
cd Downloads             # Navigate to Downloads
cd ~                     # Go to home
cd .. && cd ..          # Go up two directories
cd /opt/lampp/htdocs    # Navigate to XAMPP web folder
```

### 2. Permission Changes
```bash
chmod u+x xampp-linux-x64-8.2.4-0-installer.run    # Make installer executable
sudo chmod 777 testing    # Give full permissions to all
sudo chmod 751 testing    # Owner: rwx, Group: r-x, Others: --x
sudo chmod 761 testing    # Owner: rwx, Group: rw-, Others: --x
```

### 3. Using sudo
- Learned that some system files need `sudo` (superuser privileges)
- Used `sudo` to run installer
- Used `sudo` to change permissions on system folders

## Key Learnings:

1. **Execute Permission is Required to Run Files**
   - Downloaded files aren't executable by default
   - Need `chmod +x` or `chmod u+x` to make them runnable

2. **XAMPP Folders Need Specific Permissions**
   - `/opt/lampp/` is a system directory
   - Requires `sudo` to modify
   - `htdocs` folder needs write permissions for web development

3. **Different Permission Numbers for Different Needs**
   - Started with 777 (full access - too open!)
   - Adjusted to 751 (more secure)
   - Finally 761 (group can write, others can only execute)

4. **Command Chaining**
   - ❌ `cd .. & cd ..` (wrong - single &)
   - ✅ `cd .. && cd ..` (correct - double &&)

## Permissions Breakdown:

### 777 (rwxrwxrwx)
- Owner: read, write, execute
- Group: read, write, execute  
- Others: read, write, execute
- ⚠️ **Too permissive! Security risk!**

### 751 (rwxr-x--x)
- Owner: read, write, execute
- Group: read, execute (no write)
- Others: execute only (no read/write)
- ✅ **Better security**

### 761 (rwxrw---x)
- Owner: read, write, execute
- Group: read, write (no execute)
- Others: execute only
- ✅ **Good for web folders where group needs to edit files**

## Practical Understanding:

**Why this matters for web development:**
- WordPress/web files live in `htdocs`
- Need correct permissions for:
  - Apache to read files (r)
  - You to edit files (w)
  - PHP scripts to execute (x)

## Commands Used: 31 total
