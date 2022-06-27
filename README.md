# answers-hitchiker-theme-patches

### Add cards with copy menu
This patch creates the cards allfields-standard-with-menu, documentsearch-standard-with-menu, and help-article-with-menu.
These cards contain a menu when you hover over them which lets the user copy the result text or link from the card.
The help-article-with-menu is a fork of document-standard.

This patch also forks the iframe-common.js script and the custom-modules.js script. These files were based on Theme 1.24.

After applying the patch, the config must be updated to point to these new cards. Also, jambo.json needs to be updated to include cards and directanswercards in the partial dirs array.

### Add helpoverride and directanswers ellipses cards
This patch creates the helpoverride card, and the allfields-standard-ellipses and documentsearch-standard-ellipses directanswercards.

After applying the patch, the config must be updated to point to these new cards. Also, jambo.json needs to be updated to include cards and directanswercards in the partial dirs array.

---

## Guide for creating patch files

There are many ways to create patch files: the below is only one possibility, and will work for changes
that span multiple commits.

1. Go to the branch that already has the changes you want committed.
2. Undo all of the changes you want committed back to the base files you would apply your patch on.
3. Commit undo-ing all of the changes.
4. Do a git revert the commit you just made, which revert the "undo". This commit becomes the patch.
5. Generate the patch file with `git format-patch HEAD^` which creates a patch file for the latest commit.