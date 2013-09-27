---
author: Kyle Shipley
layout: post
title: (Anti-)Social Auth
---

One question we get from time to time, especially from our developer friends, is why we've decided to use social authentication instead of an email based solution for Paperplane. There are plenty of arguments for and against social auth, but I wanted to lay out our thoughts so you know why we made our decisions the way we did (so far).

### Too many passwords

If you're a good citizen of the internet, you probably use a different password at every site. You might even use a password manager like [1Password](https://agilebits.com/onepassword), [Dashlane](https://www.dashlane.com/en/), or [LastPass](https://lastpass.com/). This is a great start, but it means that there's no centralized place for you to track all of the services you've authorized. You could go into your password manager, figure out which services you no longer want to use, then visit each site and turn them off. This is time consuming compared to the options provided by Facebook, Twitter, and GitHub.

If you don't use a password manager, things are even bleaker. We don't see Paperplane as an "everyday" service. Rather, you log into Paperplane every week or two to create new sites or change metadata like your site's URL, then interact with us primarily via Dropbox. How many times do you forget or mistype your password for everyday sites, let alone once-in-a-while sites? We just wanted to sidestep the password reset problem and use credentials you definitely remember.

### Industry trends

You might have noticed that most sites are moving away from password-based authentication altogether. Google is exploring all sorts of crazy [alternative authentication schemes](http://www.technologyreview.com/view/510106/googles-alternative-to-the-password/). The new iPhone 5S has a high-resolution [fingerprint scanner](http://support.apple.com/kb/HT5883). Android's Ice Cream Sandwich added [facial authentication](http://www.android.com/about/ice-cream-sandwich/). Although we're not quite ready to dump the password completely, we're getting close. Just like many web developers have taken a strong stance on supporting older web browsers, we're taking a strong stance on supporting old password methodologies.

### Privacy controls

Although we ask for access to your social account, we don't use your information toward any devious ends. We're Paperplane users ourselves, and we don't want spammy wall posts or tweets any more than you do. The only information that we ask for is email address, and we take that permission very seriously. Facebook's minimum permissions seem to grant us access to your profile information, but we don't store any of that.

This emphasis on privacy can be limiting. For example, Dropbox only has two permission levels: full Dropbox access and individual App folder access. For some silly reason, you can't share App folders with other users. We had to weigh the tradeoff between not being able to share Paperplane folders and requesting overly broad permissions. In the end, we decided to hope that Dropbox does the right thing and adds sharing features rather than demanding your complete trust before you create your first site.

Another reasonable question is why we chose to include Facebook, Twitter, and GitHub auth instead of having you auth with Dropbox directly. We're revisiting this, but the short version is that Dropbox requires you to grant us access to your folder every time you log in to Paperplane. This seemed inconvenient, so we started with the best social authentication services.

### Questions? Concerns?

If we ever do something you don't approve of, let us know! Our goal is not to maximize short-term revenue and cash out. Paperplane is a service that we find immensely useful compared to S3, GitHub pages, MediaTemple, and GoDaddy's shared hosting, among others. We want to be the easiest way for you to host [landing pages](http://www.equitysteaks.com/), show off [quick experiments](http://manasword.paperplane.io/), or [host a blog with Jekyll](http://blog.paperplane.io/). (So meta!) If we're not accomplishing those goals, we'd love to know why.

If you really hate these opinions or think we could do better, let us know at [support@paperplane.io](mailto:support@paperplane.io) or on [Twitter](https://twitter.com/paperplaneio). We're "strong opinions weakly held" people, so we'd love to know if we're making a [huge mistake](http://www.youtube.com/watch?v=GwQW3KW3DCc).