# Goal

# Resources
https://virustotal.github.io/yara/

# Yara rules
File with at least 2000 rules

- When executing the file, it says Yara rules 135
- Then we looked into the corresponding rules 
- Modify candycane into candycana
- sed 's/candy/\x00\x00\x00\x00\x00/g' -i the_critical_elf_app

- Now it is rule 1056
- 2 strings need to exist in the file to pop up the yara rules
- s1 is about a libc, so we can't change it but h2 is about "program" word so we can modify it
- sed 's/program/\x00\x00\x00\x00\x00\x00\x00/g' -i the_critical_elf_app

- Now it is rule 1732
- need 10 of them
- Modified s1, s2, s3, s7, s8, s9, s11,  s12, s13, s17, s19.

sed 's/dummy/\x00\x00\x00\x00\x00/g' -i the_critical_elf_app
sed 's/naughty/\x00\x00\x00\x00\x00\x00\x00/g' -i the_critical_elf_app
sed 's/dastardly/\x00\x00\x00\x00\x00\x00\x00\x00\x00/g' -i the_critical_elf_app
sed 's/holly/\x00\x00\x00\x00\x00/g' -i the_critical_elf_app
sed 's/AFlag/\x00\x00\x00\x00\x00/g' -i the_critical_elf_app
sed 's/.note/\x00\x00\x00\x00\x00/g' -i the_critical_elf_app
sed 's/.8060/\x00\x00\x00\x00\x00/g' -i the_critical_elf_app
