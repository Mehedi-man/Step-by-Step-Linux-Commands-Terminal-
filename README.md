<img width="1366" height="768" alt="OS_Task2" src="https://github.com/user-attachments/assets/fa93df4e-dcdd-4962-9821-44626ba8513e" />

touch fruits.txt

# Insert the given content (using cat with here-document - easiest in exam)
cat << EOF > fruits.txt
This is a sample file.
It contains names of some fruits.
Mango is the national fruit.
Mango is the national fruit. Bangladesh
There are many fruits in Bangladesh.
It can be found in summer.
Sort the file.
Replace "Mango" by "Jackfruit".
EOF

# Step 3: Create a sorted version of the file
sort fruits.txt > sorted_fruits.txt

# Step 4: Replace "Mango" → "Jackfruit" in the original file (in-place)
sed -i 's/Mango/Jackfruit/g' fruits.txt

# Optional: View both files to verify
echo "Original file after replacement:"
cat fruits.txt
echo -e "\nSorted file:"
cat sorted_fruits.txt

# Step 5: Change BOTH files' permission to read-only (for owner, group, others)
chmod 444 fruits.txt
chmod 444 sorted_fruits.txt

# Verify permissions (optional - good to show in exam)
ls -l fruits.txt sorted_fruits.txt
# You should see: -r--r--r--  for both files

# Step 6: Now remove the previous (original) file
rm fruits.txt

# Final verification (only sorted_fruits.txt should remain)
ls -l
# You will see only sorted_fruits.txt with read-only permission
