To remove a commit that is 2 commits before the latest commit (`HEAD~3`) from Git history:

`git rebase -i HEAD~3`

In the text editor, change the first line from `pick <hash> <message>` to drop `<hash> <message>`. Save and exit the text editor.

`git push --force`
