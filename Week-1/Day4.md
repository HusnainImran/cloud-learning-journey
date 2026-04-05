# Day 4 - Text Manipulation & Piping (Part 1)

**Date:** Sunday, [Add date]
**Time Spent:** 1 hour
**Status:** 🟡 In Progress - Completed stdout, stdin, stderr, pipe and tee

## Commands Learned:

### 1. Output Redirection
- `>` - Redirect output to file (overwrites existing content)
  - Example: `echo Testing > file2.txt`
- `>>` - Redirect output to file (appends to existing content)
  - Example: `echo Husnain >> file2.txt`

### 2. Input Redirection
- `<` - Take input from a file
  - Example: `cat < peanuts.txt > file2.txt`

### 3. Piping
- `|` - Pipe (send output of one command to another)
  - Example: `ls -la /etc | less`
  - Example: `ls -la /etc | grep "conf"`

### 4. Tee Command
- `tee` - Write to file AND display on screen simultaneously
  - Example: `ls /etc | tee file2.txt`
  - Example: `ls -la /etc | tee file3.txt | grep "conf"`

### 5. Additional Commands Used
- `nano` - Text editor
- `clear` - Clear terminal screen
- `cat` - Read/display file contents
- `ls -la` - List files with details
- `less` - View output page by page
- `grep` - Search for patterns in text

## Practice Session (Commands 1-22):
```bash
# Started with output redirection
echo Testing > file2.txt          # Created file with "Testing"
echo Hello World > file2.txt      # Overwrote with "Hello World"

# Navigated to Desktop
cd Desktop

# More redirection practice
echo Testing > file2.txt
cat < peanuts.txt > file2.txt     # Copy peanuts.txt content to file2.txt
echo Husnain >> file2.txt         # Appended "Husnain" to file2.txt

# Edited file with nano
nano file2.txt

# Explored /etc directory
ls -la /etc                       # Listed all files in /etc
ls -la /etc | less               # Viewed output page by page

# First tee practice
ls /etc | tee file2.txt          # Listed /etc files, saved AND displayed
ls -al /etc | tee file2.txt      # Same with detailed listing

# Advanced piping with tee and grep
ls -la /etc | tee file3.txt | grep "conf"
# Saved full listing to file3.txt AND filtered for "conf" on screen

# Experimentation with complex redirections 
# Tried various combinations to understand how redirection works:
cat < file2.txt > file3.txt | cat < file 3 > grep "conf" > file2.txt
cat < file2.txt > file3.txt | cat < file3.txt > grep "conf" > file2.txt
cat < file2.txt > file3.txt | cat < file3.txt grep "conf" > file2.txt
cat < file2.txt > file3.txt | cat grep "conf" > file2.txt
cat < file2.txt > file3.txt | grep "conf" > file2.txt
```

## Key Learnings:

### 1. Redirection Operators
- `>` **overwrites** the entire file with new content
- `>>` **adds** to the end of existing file
- `<` takes input FROM a file instead of keyboard

### 2. Difference Between > and >>
```bash
echo Testing > file.txt    # File now contains: "Testing"
echo Hello > file.txt      # File now contains: "Hello" (Testing is gone!)

echo Testing > file.txt    # File contains: "Testing"
echo Hello >> file.txt     # File contains: "Testing\nHello" (both lines!)
```

### 3. Pipe vs Redirection
- **Pipe `|`** - Sends output to another COMMAND
  - `ls | grep "test"` → grep processes ls output
- **Redirect `>`** - Sends output to a FILE
  - `ls > output.txt` → saves to file

### 4. Power of Tee
- Normal redirection: You can EITHER see OR save output
  - `ls > file.txt` → Saved but can't see
  - `ls` → Can see but not saved
- With tee: You can see AND save BOTH!
  - `ls | tee file.txt` → See on screen + save to file

### 5. Chaining Commands
Successfully chained multiple commands:
```bash
ls -la /etc | tee file3.txt | grep "conf"
```
Flow: List files → Save to file3.txt → Filter for "conf" → Display filtered results

## Experiments & Learning from Mistakes:

### Complex Redirection Attempts
Tried to combine multiple redirections:
```bash
cat < file2.txt > file3.txt | grep "conf" > file2.txt
```

**What I learned:**
- Can't mix `<` `>` and `|` randomly
- Correct way: Use pipes for chaining, redirects for final output
- Better approach: `cat file2.txt | grep "conf" > file3.txt`

### Typo Corrections:
- Line 4: `cd Destop` → Corrected to `cd Desktop`
- Line 6: `file2.xt` → Corrected to `file2.txt`

## Real-World Understanding:

### How I'd Use This in WordPress Development:

**1. Monitoring logs while saving them:**
```bash
tail -f /opt/lampp/logs/error_log | tee today-errors.txt
# Watch errors live + save to file for later analysis
```

**2. Finding config files:**
```bash
ls -la /opt/lampp/htdocs/wordpress | grep "wp-config"
# Find WordPress config file
```

**3. Listing and saving file structure:**
```bash
ls -R /opt/lampp/htdocs/mytheme | tee theme-structure.txt
# See theme structure + save for documentation
```

## Additional Commands Learned:

- **grep** - Search/filter text (used in piping examples)
- **less** - Page-by-page viewer (better than cat for large outputs)
- **clear** - Clean up terminal screen
- **nano** - Edit files directly in terminal

## Questions/Things to Explore More:

1. Why did the complex redirections not work as expected?
   - Need to understand order of operations better
   
2. When to use pipe vs redirect?
   - Pipe → send to command
   - Redirect → send to file

3. Can tee append instead of overwrite?
   - Need to learn `tee -a` flag

## What's Left for Day 4:

Still need to complete:
- ✅ stdout, stdin, stderr - DONE
- ✅ pipe and tee - DONE
- ⏳ env (Environment Variables) - TOMORROW

## Status:
🟡 **Day 4 Part 1 Completed**
📅 **Next Session:** Environment variables (env command)

---

**Note:** Sunday was busy with house tasks (professional work), so completed what I could. Will finish Day 4 tomorrow and move forward. Quality learning over rushing! 💪
