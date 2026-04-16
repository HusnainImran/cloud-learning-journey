# Day 4 - Text Manipulation & Piping

**Date:** Friday, April 10, 2026
**Time Spent:** 2+ hours
**Status:** ✅ COMPLETED - All objectives achieved + bonus topics!

## Commands Learned & Mastered:

### 1. Output Redirection
- `>` - Overwrite file
- `>>` - Append to file
- `<` - Input from file

### 2. Piping & Chaining
- `|` - Pipe output to next command
- `tee` - Write to file AND display

### 3. Text Search & Filtering
- **grep** - Search for patterns
  - `grep "pattern" file` - Basic search
  - `grep -i "pattern" file` - Case-insensitive

### 4. Text Processing
- **wc** - Count lines, words, characters
  - `wc -l file` - Count lines
  - `wc -w file` - Count words
- **head** - Show first N lines
  - `history | head -5`
- **tail** - Show last N lines
  - `history | tail -5`
- **sort** - Sort lines alphabetically
- **uniq** - Remove duplicate lines (must be sorted first!)

### 5. Environment Variables
- **env** - Show all environment variables
- **echo $VARIABLE** - Display variable value
  - `$HOME` - Home directory path
  - `$USER` - Current username
  - `$PATH` - System executable paths
  - `$SHELL` - Current shell program

### 6. File Viewing
- **more** - Page through text (old style)
- **less** - Better pager (can scroll back)
- **cat** - Display entire file
  - `cat > file` - Create file (Ctrl+D to save)
  - `cat >> file` - Append to file

### 7. BONUS: Process Management Preview
- **ps** - Show processes
- **ps aux** - Show all processes with details

## Practice Session (Commands 402-469):

### Phase 1: Redirection Practice (402-422)
```bash
# Output redirection
echo Testing > file2.txt
echo Hello World > file2.txt          # Overwrites previous
cat < peanuts.txt > file2.txt         # Copy file content
echo Husnain >> file2.txt             # Append

# Piping practice
ls -la /etc | less                    # View with pager
ls /etc | tee file2.txt               # Save and show
ls -la /etc | tee file3.txt | grep "conf"  # Chain commands

# Experimentation with complex redirections
cat < file2.txt > file3.txt | grep "conf" > file2.txt
# (Tried various combinations to understand flow)
```

### Phase 2: Text Search & Processing (423-459)
```bash
# grep practice
grep "brown" file2.txt
grep "fox" file2.txt
grep -i apple fruits.txt              # Case-insensitive

# Tested grep with ls (learned it doesn't work that way)
ls file2.txt | grep "fox"             # Wrong approach
ls -la file2.txt | grep "fox"         # Still wrong

# head and tail
history | head -5                     # First 5 commands
history | tail -5                     # Last 5 commands
history | sort                        # Sort all history

# Process viewing
ps                                    # My processes
ps aux                                # All system processes

# File creation methods
cat > fruits.txt                      # Create and type content
cat >> fruits.txt                     # Append content
nano fruits.txt                       # Edit in text editor

# Word count practice
wc -w fruits.txt                      # Count words
wc -l fruits.txt                      # Count lines

# Sort and unique
sort fruits.txt                       # Sort alphabetically
sort fruits.txt | uniq                # Remove duplicates
```

### Phase 3: Environment Variables (460-469)
```bash
# View all environment variables
env

# Access specific variables
echo $HOME                            # /home/husnain
echo $USER                            # husnain
echo $PATH                            # System paths
echo $SHELL                           # /bin/bash (or similar)

# Tested undefined variables
echo $NAME                            # (empty - not set)

# Experimentation with formatted output
echo /*==============*\ echo System Details
# (Tried creating formatted headers)
```

## Key Learnings:

### 1. Pipe vs Redirection
- **Pipe `|`** sends output to another COMMAND
  - `ls | grep "txt"` → grep processes ls output
- **Redirect `>`** sends output to a FILE
  - `ls > output.txt` → saves to file

### 2. grep Only Works on Text Content
```bash
# WRONG:
ls file.txt | grep "fox"              # grep searches "file.txt" string, not file content

# RIGHT:
grep "fox" file.txt                   # grep searches INSIDE file
cat file.txt | grep "fox"             # Also works
```

### 3. wc Counts the File, Not Patterns
```bash
# WRONG:
wc -l "apple" fruits.txt              # Tries to count file named "apple"

# RIGHT:
grep "apple" fruits.txt | wc -l       # Count lines containing "apple"
```

### 4. sort + uniq = Remove Duplicates
```bash
# Must sort FIRST, then uniq
sort fruits.txt | uniq                # Removes adjacent duplicates
# uniq alone won't work on unsorted data
```

### 5. Environment Variables Syntax
```bash
# Variables are case-sensitive
echo $USER                            # ✅ Works
echo $User                            # ❌ Empty (wrong case)
```

### 6. Creating Multi-line Files
Three methods discovered:
```bash
cat > file.txt          # Type, then Ctrl+D to save
cat >> file.txt         # Append mode, Ctrl+D to save
nano file.txt           # Full editor, Ctrl+X to exit
```

## Experiments & Discoveries:

### Experiment 1: Complex Piping (Lines 436-438)
**Attempt:**
```bash
less -n file2.txt | tee grep -i "fox" | wc -l
```
**Goal:** View file, search, and count in one command
**Issue:** Syntax error - tee can't execute grep as parameter
**Correct approach:**
```bash
cat file2.txt | grep -i "fox" | wc -l
# OR simply:
grep -i "fox" file2.txt | wc -l
```

### Experiment 2: grep with ls (Lines 428-429)
**Attempt:**
```bash
ls file2.txt | grep "fox"
```
**Lesson:** This searches the filename "file2.txt" for "fox", not the file's content
**Correct:** `grep "fox" file2.txt`

### Experiment 3: wc with Pattern (Lines 453-454)
**Attempt:**
```bash
wc -l "apple" fruits.txt
```
**Lesson:** wc counts the file itself, not occurrences of a pattern
**Correct:** `grep "apple" fruits.txt | wc -l`

## Real-World Applications:

### WordPress/Web Development Use Cases:

**1. Find errors in logs:**
```bash
grep "error" /opt/lampp/logs/error_log | wc -l
# Count how many errors today
```

**2. Find which files use a function:**
```bash
grep -r "wp_enqueue_style" /opt/lampp/htdocs/mytheme | wc -l
# Count occurrences across all files
```

**3. Monitor recent activity:**
```bash
tail -20 /opt/lampp/logs/access_log | grep "POST"
# See recent POST requests
```

**4. Check running services:**
```bash
ps aux | grep apache
ps aux | grep mysql
# See if web server and database are running
```

**5. Sort and analyze data:**
```bash
cat access.log | grep "404" | sort | uniq -c | sort -r
# Find most common 404 errors
```

## Commands Mastered: 20+

New commands this session:
- grep, wc, head, tail, sort, uniq
- env, echo $VARIABLE
- ps, ps aux
- more, less (advanced usage)
- cat >, cat >> (file creation)
- Complex piping chains

## Status:
✅ **Day 4 COMPLETED 100%**
✅ **Bonus: Explored process management (ps)**
✅ **Ready for Day 5!**

---

**Next:** Process Management & System Monitoring (Day 5)

## Self-Assessment:

**Confidence Level:** ⭐⭐⭐⭐☆ (4/5)

**What I'm comfortable with:**
- Output redirection (>, >>)
- Basic piping
- grep for searching
- head/tail for viewing portions
- Environment variables

**What I need more practice with:**
- Complex multi-command pipes
- Advanced grep patterns
- Combining multiple text processing tools
- When to use each tool vs others

**Hours spent:** ~2 hours (estimated from command count: 67 commands)

**Bonus achievement:** 🏆 Self-directed experimentation and learning!
