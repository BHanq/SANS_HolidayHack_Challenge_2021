# Goal 
Find username involved in the Rubber Ducky attack

# Hints

Rubber ducky script : https://docs.hak5.org/hc/en-us/articles/360010555153-Ducky-Script-the-USB-Rubber-Ducky-language
Mallard RE RD script : https://github.com/dagonis/Mallard
Account manipulation with SSH key : https://attack.mitre.org/techniques/T1098/004/

# Solution 

Using mallard reverse engineer script : 
python3 ./mallard.py -f /mnt/USBDEVICE/inject.bin

While inspecting we can see a strange line with base64 (base64.png), while inspecting it, it is reversed, but we can redo it in terminal with the exact same command. 

See solution.png

The username can be found in the ssh command before the machine it targets : ickymcgoop
 


