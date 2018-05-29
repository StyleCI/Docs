# Automation

StyleCI provides deep integration with GitHub's status API, meaning that we can provide reports on pull requests. You have 2 awesome options to choose from.

<a name="1-let-us-do-everything-for-you"></a>
## 1. Let us do everything for you

Now, if the contributor's code is failing our checks, this is actually totally fine, because, after merging the PR, we can send you a pull request to fix the code. How awesome is that! By default, we won't send this PR without asking, but you can simply toggle this in your settings, to get us to automatically send a PR without you asking, and we have another setting that can even get us to automatically merged the PR too!

Manual triggering of automatic fix PRs can be done from the analysis page, and automatic sending/merging of these fix PRs can be enabled from the settings page.

<a name="2-youd-like-more-control"></a>
## 2. You'd like more control

If you'd prefer to make sure everything's just right before merge, or you prefer to commit your own fixes, that's super easy too. On every analysis page, we provide a diff download link where you can download a diff that can be applied using git apply. This can be useful if you'd like the contributor to fix the CS issues, or useful if you'd like to merge their PR using Gush, and fix the issues as you merge. So powerful!

You can even use GitHub's [protected branches](https://help.github.com/articles/about-protected-branches/) feature to prevent bad changes getting merged.

> {info} We're in the process of migrating our documenation. You can find the original docs [here](https://styleci.readme.io/docs/automation).
