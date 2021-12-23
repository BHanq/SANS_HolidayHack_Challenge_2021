# Objective 2 

# Instructions
Someone tampered (modified) a file. Which one is it ? 


# Hint

It is mentioned that they installed exiftool. So we probably need it ! 

# My solution

I checked the 3 first files, they were all created & modified on the "filename date" date. 

Then I used exiftool with a pipe to check which file has been modified after its creation date.

Command used : 
exiftool * | grep -v "Zip" | grep -e "File Name" -e "Modify Date"

- Exiftool displays all the metadata of the files
- grep -v : remove the lines with "Zip" in it
- grep -e : Display lines with Modify date OR File Name in them

# Output

See output.png to see the result
