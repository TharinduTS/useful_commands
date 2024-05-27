# useful_commands

# Copy files with rsync
```bash
rsync -axvH --no-g --no-p premacht@graham.computecanada.ca:/scratch/premacht/python_projects_2023/hetero_comparison_4_pops/combined_summaries .
```
one drive directory on windows ubuntu
```
cd /mnt/c/Users/thari/OneDrive\ -\ McMaster\ University/for_lab_and_research/Tharindu_on_Mac/lab
```

# Rename files with sed
```bash
find . -type f -name '*.bam' | while read FILE ; do     newfile="$(echo ${FILE} |sed -e 's/xxx/yyy/g')" ;     mv "${FILE}" "${newfile}" ; done
```

# touch all files
```bash
find . > all_files_list

 

while IFS= read -r line <&3; do

  line=${line%$'\r'} # trim DOS newlines

  printf 'touching following line: %s\n' "$line" >&2

  touch "$line"

done 3<all_files_list
```
Use sed to find and replace

all occurences
```
sed -e 's:XXX:YYY:g'
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
# R list to comma seperated
```
paste(noquote(shortened_sample_list), collapse=",")
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
 
# set current path as wd
```
library("rstudioapi") 
setwd(dirname(getActiveDocumentContext()$path))
```

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
```
# python
If you want to use python and cannot use modules try following creating virtual environment
this example is with numpy
```bash
module load python/3.8.2
virtualenv --no-download ~/ENV
source ~/ENV/bin/activate
pip install --no-index --upgrade pip
pip install numpy --no-index
```
Then work as you want and,

when you want to exit the environment,

```bash
(ENV) [name@server ~] deactivate
```
# qgis

Always use google sheets to add cordinate files. Mac handles csv s and tsvs differently and qgis cannot understand that
