This version of phpcomplete parses method's phpdoc so you can see the description, params, return and throws in the top window.

Requirements:
------------
* Exuberant ctags: You need it to generate class tags.
* Vim-Python: I've put python code in phpcomplete.vim

Installation:
-------------
1- Copy phpcomplete.vim in your .vim/autoload/ dir

2- Generate a tags file with exuberant ctags. You can use this command to generate your tag file:
```
#!/bin/bash
exec ctags -f tagsFile.txt \
-h ".php" -R \
--exclude="\.svn" \
--totals=yes \
--tag-relative=yes \
--PHP-kinds=+cf \
--fields=+S \
--regex-PHP='/abstract class ([^ ]*)/\1/c/' \
--regex-PHP='/interface ([^ ]*)/\1/c/' \
--regex-PHP='/(public |static |abstract |protected |private )+function ([^ (]*)/\2/f/' \
--exclude='*frontend/gesca/shared/frontend_data/*' \
--exclude='*.js' \
--exclude='*.html'
```

3- load tags file from vim: ":set tags=tagsFile.txt"

4- use ctrl-x-ctrl-o to see autocomplete suggestions and you will see phpdoc info on the top screen :D
