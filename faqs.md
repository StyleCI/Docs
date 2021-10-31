# Frequently Asked Questions

<a name="cant-access-private-repos"></a>
## I can't access my team's private repos

By default, StyleCI only requests public repo scopes from GitHub. If you are getting error 403 errors, or your team's private repos are not showing up, then it is likely that you need to enable private repo access. This is free to do, and can be done from the home page, when logged in, or from the [profile page](https://github.styleci.io/profile).

<a name="enable-full-automation"></a>
## How do I enable all StyleCI's automation

By default, StyleCI will not automatically apply its fixes to your codebase unprompted. This is to allow you to initially review StyleCI's fixes, and possibly tweak the configuration. Once you are happy with the settings, you can choose from one of our automation modes witihn the settings page for the repo on StyleCI.

<a name="apply-fixes-locally"></a>
## How do I apply StyleCI's changes locally

StyleCI is designed so that you don't need to worry about doing this - we can automatically apply our fixes right after you push. However, for those who really want it, we have a CLI tool that can be used to apply our fixes to your code before you push. All we require is that you have PHP 7.2 or higher installed on your machine, and we can fix all your PHP, JS, CSS, Vue.js, and Python code, right then and there! Our CLI tool is available at [https://github.com/StyleCI/CLI](https://github.com/StyleCI/CLI).

<a name="turn-off-notifications"></a>
## How do I turn off notification emails

Don't want to get emailed when things change? No problem. You can configure your notification level on your profile page(s). Please visit [StyleCI for GitHub](https://github.styleci.io/profile), [StyleCI for GitLab](https://gitlab.styleci.io/profile), or [StyleCI for Bitbucket](https://bitbucket.styleci.io/profile) to choose from the 3 notification levels available.

<a name="not-receiving-email-notifications"></a>
## Why am I not receiving notification emails

If you're not receiving any of our notification emails, it could be down to one of several issues.

### Whitelist us

A good starting point is to ensure that the email address we use to send emails to you isn't blacklisted or marked as spam by your email provider. We may send mail from the following email addesses:

* Customer service and support emails are sent from support@styleci.io;
* Transactional and notification emails are sent from notify@styleci.io;

Our order process is conducted by our online reseller & Merchant of Record, Paddle.com, who also handle order related inquiries and returns. They may send emails from @paddle.com and @paddle.net email addresses.

### Check your email address

We send emails to email address that you set as your primary email on GitHub, GitLab or Bitbucket. You can check the email address that we have for you by visiting your profile page at [StyleCI for GitHub](https://github.styleci.io/profile), [StyleCI for GitLab](https://gitlab.styleci.io/profile), or [StyleCI for Bitbucket](https://bitbucket.styleci.io/profile). You can also configure your notification preferences from this page.

<a name="keep-a-change-log"></a>
## Do you keep a change log?

Yes, we document all major changes we make on our [blog](https://blog.styleci.io/).
