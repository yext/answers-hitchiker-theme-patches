## Apply a Diff File to your Yext Search Frontend


### Results Actions for Salesforce, Zendesk, Freshdesk, Freshservice


## Overview

To get the most out of your Agent Desktop integration you’ll likely want to take advantage of Yext Result Actions within your case view. Depending on the platform, result actions will allow agents to execute a variety of tasks in a single click.

Currently result actions are only supported for direct answer cards and help article cards. To expand result actions to further cards you’ll need to manually add them.

By adding these patches to your experience, a kabob will be added to the aforementioned cards, which when hovered on, will display a set of result action options. Many actions (such as attach to case, send to chat, etc.) will be dependent on the parent page and will not work within the production URL alone.

These patches also fork the iframe-common.js script and the custom-modules.js script. These files were based on Theme 1.24.

Select your integration to see which actions actions are supported.


## Application Instructions

**These patches are designed to be applied to a fresh answers repo. Any changes you’ve made to your files may be overwritten by applying a diff file.**



1. Select the directory of the third-party platform your Yext Search Experience will live in
2. Select the patch file
3. Click “raw”

    
![](https://lh3.googleusercontent.com/xkKB05Us_fA77WA594Tyu4VLY1xAdVjV3a9WquQj8D1nJCXiqmB_N7HB26CMDdxTd-y_0IX740Xn9OrcXf-wXGcIx0bwhfpXoXAr9n87ZR6mbQyiHT1xai6PX1z9M5AtG1wIenORq97_JlHUok0)



4. Copy the page URL. It should begin with “raw.github…”
5. Navigate to your Answers Experience code editor
6. Click into Tools > Apply Diff


![](https://lh5.googleusercontent.com/Z27EF2FC2TElCj04fh2a3hDLXHLq2NlyYQasG6_ADIEqeqb5CvGxVX0T2j6m0Cif5sLdRu37iw88wrXkE71Fh1ChoK6_3s18mEduK1qaJZaQy6qClMCND8i_vA9MsQsyIYlQ1qoT_Qsj1iQbiEc)


7. Paste the copied URL and click Apply
8. Update your help article vertical config file to point to the new help article card, and your index.json file to point to the new direct answer cards.
9. Update your jambo.json file to include the `directanswercards `array.


## Guide for creating patch files

There are many ways to create patch files: the below is only one possibility, and will work for changes that span multiple commits.



1. Go to the branch that already has the changes you want committed.
2. Undo all of the changes you want committed back to the base files you would apply your patch on.
3. Commit undo-ing all of the changes.
4. Do a git revert the commit you just made, which revert the "undo". This commit becomes the patch.
5. Generate the patch file with git format-patch HEAD^ which creates a patch file for the latest commit.