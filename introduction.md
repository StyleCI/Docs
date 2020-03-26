# StyleCI Docs

StyleCI is a continuous integration service which **automatically enforces** your code style preferences. Never again waste your developers' time on maintaining and configuring custom code style fixing tools and CI services, or their time reviewing code style within pull requests. Simply enable StyleCI, apply our fixes, then enable our full automation mode!

We support both your open and closed source repos from **GitHub**, **GitLab** or **Bitbucket**. By analyzing every push or pull request made on your codebase, StyleCI ensures that your code is always written against the standards you want it to be. StyleCI supports **PHP**, **JS**, **CSS**, **Vue.js**, **Python** and more. For **Laravel** users, StyleCI is used by the framework to enforce its own code style guidelines automatically, and Laravel applications additionally ship with a `.styleci.yml` config file to help you get started.

<a name="getting-started"></a>
## Getting Started

To get started, click the Login button on our homepage. You'll then have a choice of logging in with GitHub, GitLab, or Bitbucket. Before you continue, be sure to review our terms of service and privacy policy.

> {info} If you are using GitHub, be sure to allow StyleCI access to any repositories that require third party access to be approved.

<a name="private-repo-support"></a>
## Private Repo Support

PHP support in StyleCI is free for all open source projects. We offer different plans for private repositories and support for PHP, JS, CSS, Vue.js, Python, and more! You can upgrade or downgrade your plan on your account page.

You can still access private repos from the open source plan if someone else in your organization is subscribed to a paid plan that supports private organizations. To view these repos, visit the the Profile tab and choose "Private" under the Access heading. This will allow us to read your private repo memberships, after you've approved this change on GitHub.

<a name="your-repos"></a>
## Your Repos

All your repos are listed in the Repos tab of your account page. You can enable repos you want us to analyze here. After enabling a repo, you can visit it by clicking the "Show analyzes" button. At this point, you have the option to configure its settings, or go ahead and press that "Analyze Now" button. You can select the branch you want to look at through the branch select drop-down on the left. For information about configuration, please check out the [configuration](configuration) section of our docs.

You can view all the repos enabled on our system by clicking on our [badge](badges). This will take you to our homepage, where you'll find summaries of all your repos' statuses.
