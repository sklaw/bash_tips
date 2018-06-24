# bash_tips

```bash
grep -rl console.log .| xargs sed -i /.*console.log.*/d

git diff -w --diff-filter=M --ignore-space-change -B

grep -Prn app -e '(?!file).*\.xml[^a-zA-Z'"'"'"]' --color=always | less -r

grep -Prl -e "[^\.\-a-zA-Z]alt ? ?=" app/ | xargs sed -i -e 's@[^\.\-\W]alt\ \?\ \?=@\ title=@g'


grep -Prl -e 'sLoginUser != "user"' | xargs sed -i -e 's@sLoginUser\ !=\ "user"@sLoginUser\ !=\ "user"\ \&\&\ sLoginUser\ !=\ "user"@g'



#view commits that did something to a file 
git log -p -w --follow edit.html



grep -Prl -e 'sLoginUser != "user"' | xargs sed -i -e 's@sLoginUser\ !=\ "user"@sLoginUser\ !=\ "user"\ \&\&\ sLoginUser\ !=\ "user"@g'

find ./ -name "*.css" -type f -exec sed -i 's/\t/    /g' {} \;
find . -name "*.css" -type f -exec dos2unix {} \;

grep -Prl -e "Product" . | xargs sed -i -e "s/Product/System/g"

#clean ass for specific extension files
find . -name "*.py" | xargs grep -l -e "varSubjectId" | xargs sed -i -e "s/varSubjectId/subjectId/g"


git remote set-url dev_repo ssh://user@127.0.0.1:1234/abs/path

git clone ssh://user@127.0.0.1:1234/abs/path

scp -P 1234 jquery.cookie-1.4.1.min.js user@127.0.0.1:/abs/path

grep -rl app/datastore/ -ie "[a-zA-Z]\+ in (" | xargs sed -i -e "s/\([a-zA-Z]\+\) in (/CAST(\1 as BINARY) IN (/g"

grep -rl app/ -e "if *(\$[a-zA-Z]\+\[.*\])"  | xargs sed -i -e "s@if *(\(\$[a-zA-Z]\+\)\[\(.*\)\])@if (array_key_exists(\2, \1))@g"s

# Kill processes with grep
ps -fe | grep python.*process_runner | grep -v grep | awk '{print $2}' | xargs kill -9

# Grep searched files and sort them by one of the space-seperated columns
find . -name introspection_model_info -printf '%p' -exec grep threshold {} \; | sort -n -k 6 -r
find . -path "*skill 5/introspection_model_info" -printf '%p' -exec grep threshold {} \; | sort -n -k 6 -r

# Find msg files and append a line to them
find . -name "*.msg" -exec sh -c "echo 'Header header' >> {}" \;

# udev rule that connects robotiq force sensor and more
KERNEL=="ttyUSB?", SUBSYSTEM=="tty", ATTRS{idVendor}=="0403", ATTRS{idProduct}=="6015", ATTRS{serial}=="DAWYTWZ1", MODE="0666", GROUP="dialout", SYMLINK+="robotiqforcesensor"


```


