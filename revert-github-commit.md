### Revert the full commit
Sometimes you may want to undo a whole commit with all changes. Instead of going through all the changes manually, you can simply tell git to revert a commit, which does not even have to be the last one. Reverting a commit means to create a new commit that undoes all changes that were made in the bad commit. Just like above, the bad commit remains there, but it no longer affects the the current master and any future commits on top of it.

    git revert {commit_id}

### About History Rewriting

#### Delete the last commit
Deleting the last commit is the easiest case. Let's say we have a remote _origin_ with branch _master_ that currently points to commit _dd61ab32_. We want to remove the top commit. Translated to git terminology, we want to force the _master_ branch of the _origin_ remote repository to the parent of _dd61ab32_:

    git push origin +dd61ab32^:master

Where git interprets `x^` as the parent of `x` and `+` as a forced non-fastforward push. If you have the master branch checked out locally, you can also do it in two simpler steps: First reset the branch to the parent of the current commit, then force-push it to the remote.

    git reset HEAD^ --hard

    git push origin -f

---

This document is inspired by http://christoph.ruegg.name/blog/git-howto-revert-a-commit-already-pushed-to-a-remote-reposit.html - Thank you.
