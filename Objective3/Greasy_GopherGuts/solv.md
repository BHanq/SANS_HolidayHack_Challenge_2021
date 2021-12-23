# Goal 
Parse nmap scan : "bigscan.gnmap"

# Cheatsheet 
https://ryanstutorials.net/linuxtutorial/cheatsheetgrep.php

# Question 1 

What port does 34.76.1.22 have open ? 

## Solution 

cat bigscan.gnmap | grep 34.76.1.22

TCP 62078

# Question 2 

What port does 34.77.207.226  have open ? 

## Solution 

cat bigscan.gnmap | grep 34.77.207.226

8080

# Question 3 

How many hosts appear "Up" in the scan ?

## Solution 

cat bigscan.gnmap | grep -e "Status: Up" | wc -l

26054

# Question 4 

How many hosts have a web port open (80, 443, 8080)

## Solution 

cat bigscan.gnmap | grep -e "443/" -e "80/" -e "8080/" | wc -l

Don't forget the / because it could take other number of a line (here it specify ports)
14372

### Their solution
grep -E "(80|443|8080)/open" bigscan.gnmap | wc -l
If you want to be MORE correct, you might use "(\s8080|\s443|\s80)/open" to ensure you don't snag ports like 50080, but there weren't any in this file.
# Question 5 

How many hosts with status Up have no detected open tcp ports


## Hint 
I was really stuck on this, I didn't spot that no open ports doesnt give a "Ports open line"
parsiya (on discord)
 — 
11/12/2021
There are two types of lines in the file (actually 3 if you count the comments in the 1st and last lines). One is Host: 1.2.3.4 ()    Status: Up and the other is Host: 1.2.3.4 ()    Ports: .... If a host is up but has no open ports, you only see it once. To find out how many hosts are up but have no open ports you have to figure out how many hosts appear only once in the file. You can do this in different ways.
## Solution

cat bigscan.gnmap | grep -e "Up" | wc -l
26054

cat bigscan.gnmap | grep -e "Ports" | wc -l
25652

26054-25652=402

402
### Their solution
echo $((`grep Up bigscan.gnmap | wc -l` - `grep Ports bigscan.gnmap | wc -l`))

# Question 6 
What's the greatest number of TCP ports any one host has open

## Solution 

egrep -n "^.{$(wc -L < bigscan.gnmap)}$" bigscan.gnmap
Longest line of a file :  https://askubuntu.com/questions/532584/how-does-this-egrep-command-find-the-longest-line-in-a-file

And then count each service : 
12

### Their solutions
grep -E "(open.*){12,}" bigscan.gnmap | wc -l && grep -E "(open.*){13,}" bigscan.gnmap | wc -l

awk 'BEGIN {print}{print gsub(/open/,"") ""}' bigscan.gnmap | sort -nr | head -1

