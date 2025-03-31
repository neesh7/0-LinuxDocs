## Searching files and directories
```bash
$ locate city.txt # easiest way to locate file 
# there is downside to use locate command as it uses mlocate.db database.if the file was created recently this command may not be of very help.

$ sudo updatedb # update the db so locate works perfectly
```

#### Find command
```bash
$ find /home/neesh -name city.txt # we can also use find commands to search for files
```
## Grep Command
    - This command is used to perform more advance search
    - This command is case sensetive so use -i to ignore cases.

```bash
$ grep second sample.txt # searchs for string "second" inside sample.txt
$ grep -i capital sample.txt # searchs for string "capital" inside sample.txt with casefolded. -i flag used to ignore case

$ grep -r "lemon" /home/neesh # it searchs for all file which contains lemon string inside the provided directory

$ grep -v "printed" sample.txt # it will print those line which doesn't contains provided string

$ grep -w exam hello.txt # this search is used for exact word match. -w means wholeword

$ grep -vw exam examples.txt # it will print those lines which doesnt contains exam whole word in it.

$ grep -A1 Arsenal premier-table.txt # prints the matching line and one line after matching line
$ grep -B1 Arsenal premier-table.txt # prints the matching line and one line before matching line
$ grep -A1 -B1 Arsenal premier-table.txt # print the matching line and one line before and after the matching line.
```