# useful_commands
# Rename files with sed
```bash
find . -type f -name '*.bam' | while read FILE ; do     newfile="$(echo ${FILE} |sed -e 's/xxx/yyy/g')" ;     mv "${FILE}" "${newfile}" ; done
```

# touch all files
```bash
find . -type d > all_files_list

 

while IFS= read -r line <&3; do

  line=${line%$'\r'} # trim DOS newlines

  printf 'touching following line: %s\n' "$line" >&2

  touch "$line"

done 3<all_files_list
```
# list file names seperated by a space
```bash
ls ../all_bam_files/ | tr "\n" " "
```
# List into comma seperated values
```text
Open Word
"Paste special" as text only
Select the data in Word (the one that you need to convert to text separated with ,), press Ctrl-H (Find & replace)
In "Find what" box type ^p
In "Replace with" box type ,
Select "Replace all"
```
