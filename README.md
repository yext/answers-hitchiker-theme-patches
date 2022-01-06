# answers-hitchiker-theme-patches

### Add cards with copy menu
The patch creates the cards allfields-standard-with-menu, documentsearch-standard-with-menu, and help-article-with-menu.
These cards contain a menu when you hover over them which lets the user copy the result text or link from the card.
The help-article-with-menu is a fork of document-standard.

This patch also forks the iframe-common.js script and the custom-modules.js script. These files were based on Theme 1.24.

After applying the patch, the config must be updated to point to these new cards. Also, jambo.json needs to be updated to include cards and directanswercards in the partial dirs array.