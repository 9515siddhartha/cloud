1)question
answer-----------------------------------------------------------------------------
#!/bin/bash
function file_count()
 {
   local NUMBER_OF_FILE=$(ls -l | wc -l)
    echo "$NUMBER_OF_FILE"
 }
file_count
-----------------------------------------------------------------------------------------------------------------------------------------
2)question answer---------------------------------------------------------------------------------./
find / -name "myfile.txt"

3question------------------------------------------------
answer--------------------------------------------------------------------------
#!/bin/bash

# Check if the directory name is provided
if [ "$#" -ne 1 ]; then
echo "ERROR: Please provide the directory name as an argument."
exit 1
fi

# Store the directory name
dir=$1

# Check if the directory exists
if [ ! -d "$dir" ]; then
echo "ERROR: The specified directory does not exist."
exit 1
fi

# Remove all permissions for groups and others
chmod o-rwx,g-rwx "$dir"

# Set all permissions for the owner
chmod u+rwx "$dir"

# Loop through all files in the directory
for file in "$dir"/*; do
# Remove all permissions for groups and others
chmod o-rwx,g-rwx "$file"

# Set all permissions for the owner
chmod u+rwx "$file"
done
.....
