# Linux Fundamentals: Read and Write Text Files

## Suggested command flow:

touch notes.txt

echo "Line 1" > notes.txt

echo "Line 2" >> notes.txt

echo "Line 3" | tee -a notes.txt

cat notes.txt

head -n 2 notes.txt

tail -n 2 notes.txt

## Example

### Create a new file

touch notes.txt

### Write first line

echo "Linux is powerful" > notes.txt

### Append second line

echo "DevOps uses Linux daily" >> notes.txt

### Append third line using tee

echo "File handling is important" | tee -a notes.txt

### Added more lines

echo "cat reads full file" >> notes.txt

echo "head shows starting lines" >> notes.txt

echo "tail shows ending lines" >> notes.txt

echo "tee writes and displays output" >> notes.txt

### Read complete file

cat notes.txt

### Read first 2 lines

head -n 2 notes.txt

### Read last 2 lines
tail -n 2 notes.txt

## OUTPUT 

![alt text](<file io.png>)