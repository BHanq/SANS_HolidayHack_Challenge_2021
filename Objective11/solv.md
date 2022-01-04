# Goal 
Find the trolls complaining about human using a Wireshark analysis 

# Hints
https://wiki.wireshark.org/DisplayFilters : Different from BPF capture filters, Wireshark's display filters can find text with the contains keyword - and evil bits with ip.flags.rb.
https://datatracker.ietf.org/doc/html/rfc3514 RFC3514 defines the usage of the "Evil Bit" in IPv4 headers.

# Filter used
We need to get only Post forms and read the complaints

http.request.method == "POST" 

# Solution 
Read the complaints and find the 3 names of troll complaining about a human. 

They are all complaining about humans but only 3 of them does on the same one. Lady of room 1024.

Their troll names are : Flud Hagg Yaqh

