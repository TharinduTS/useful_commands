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

  sleep 1

done 3<all_files_list
```
