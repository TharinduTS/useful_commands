# useful_commands

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
