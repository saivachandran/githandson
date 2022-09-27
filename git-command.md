# If I understand the question correctly, you simply want to "undo" the git add that was done for that file.

# If you need to remove a single file from the staging area, use
```
git reset HEAD -- <file>
```
# If you need to remove a whole directory (folder) from the staging area, use
```
git reset HEAD -- <directoryName>
```
# Your modifications will be kept. When you run git status the file will once again show up as modified but not yet staged.
