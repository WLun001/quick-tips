### quick tips for git
- How to make Git “forget” about a file that was tracked but is now in .gitignore?
- Undo a git add




## How to make Git “forget” about a file that was tracked but is now in .gitignore?
```
git rm -r --cached . 
git add .
git commit -am "Remove ignored files"
```

## Undo a git add .
```
git reset
```
