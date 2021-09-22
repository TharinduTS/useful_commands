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

# extract parts of variables in bash
```bash
${MYVAR#pattern}     # delete shortest match of pattern from the beginning
${MYVAR##pattern}    # delete longest match of pattern from the beginning
${MYVAR%pattern}     # delete shortest match of pattern from the end
${MYVAR%%pattern}    # delete longest match of pattern from the end
```
# execute a command substituting a word

do this after running the first script with string1 to run the same script with string2 - This only replaces the first instance of string1
```
^string1^string2^
```
if you want to change all instances
```
!!:gs/string1/string2/
```
Quick substitution. Repeat the last command, replacing string1 with string2
# Check chromosomes in bam files
```bash
samtools idxstats JM_no_label1_Draken_CCACGT_cuttrim_sorted_final_s_only.bam | grep 'chr'
```
# copy only selected files from all the sub directories keeping directory structure
```bash
find directory_to_look -name '*.wildcard_here' | cpio -pdm output_folder_here
```
# R wildcards can be found here;
https://www.r-studio.com/Unformat_Help/regularexpressions.html

# R scripts give unexpected errors??
 Try updating all packages
 
# Installing R packages on computecanada

first load this module
```bash
module load gcc/9.3.0 r/4.1.0
```
open r
```
R
```
use install.packages('package_name')
```
and then follow steps to create a personal library
