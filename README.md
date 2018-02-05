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

```
