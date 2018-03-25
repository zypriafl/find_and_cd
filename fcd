#!/bin/bash
echo "Looking for '$1'... "

# Search for Folder and sort by depth while removing Warnings
result=$(find .  -type d -name "$1" -printf "%d\t%p\n" 2> /dev/null | sort -n)

# Print results
printf "$result\n"

# Check if results were found
if [ ${#result} -eq "0" ]
	then 
	echo "No results"
else 
	# If results were found, cd to first result
	first_result=$(echo "$result" | head -1 | cut -f2)
	printf  "\nGo to $first_result\n"
	cd "$first_result"

	# Return shell that point to desired directory
	exec bash
fi
