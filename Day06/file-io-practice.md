# Create the file
touch notes.txt

# Write 3 lines into the file
echo "Line 1: Getting started with DevOps" > notes.txt
echo "Line 2: Learning Linux basics" >> notes.txt
echo "Line 3: Practicing file redirection" | tee -a notes.txt

# Add a few more lines for total 8–12 lines
echo "Line 4: Using cat to read files" >> notes.txt
echo "Line 5: Using head to read top lines" >> notes.txt
echo "Line 6: Using tail to read bottom lines" >> notes.txt
echo "Line 7: Combining commands for practice" >> notes.txt
echo "Line 8: End of notes" >> notes.txt

# Read the full file
cat notes.txt

# Read first 2 lines
head -n 2 notes.txt

# Read last 2 lines
tail -n 2 notes.txt
