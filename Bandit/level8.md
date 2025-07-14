millionth       dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc

## Grep Command 

grep [ option ] PATTERN [ file ]

1. Search for a word in a file 
 grep "hello" file.txt 

2. Ignore Case 
 
 grep -i "hello" file.txt

3. show line number with matches 

 grep -n "error" log.txt 

4. Count occurances 
 grep -c "404" access.log 

5. Invert Matches 
 grep -v "success" output.log 

6. Recursive search in all files in a directory 

grep -r "TODO"

7. Mathc full word 

grep -w "cat" pets.txt

8. USe Regular expression 

grep "gr[ae]y" color.txt

9. Show 3 lines before after the Match +

grep -A 3 "error" logfile.txt    # After
grep -B 2 "error" logfile.txt    # Before
grep -C 1 "error" logfile.txt    # Context (before + after)
