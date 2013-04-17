---
author: Kyle Shipley
layout: post
---

We recently launched [paperplane.io](http://www.paperplane.io), a service that makes hosting web sites super easy. We've been using it a lot for quick experiments like [manasword.paperplane.io](http://manasword.paperplane.io/), wherein I attempted to convince a friend to replay SNES Action-RPG classic Secret of Mana and played with CSS3 border-images. It's also our go-to tool for landing pages, including [the re:build conference](http://www.rebuildconf.com/) and [Equity Steaks](http://www.equitysteaks.com).

You'll notice that those last two pages are on custom domains. Luckily, paperplane has a fairly painless process for connecting that great new domain you purchased to a Dropbox folder. It's a few more steps than using a paperplane.io subdomain, but with the right hosting partner, it can be pretty painless. If you haven't signed up for [paperplane.io](http://paperplane.io) yet, now would be a good time to familiarize yourself. We'll wait for you.

Back? Great. Let's get started.

Here's a fresh paperplane dashboard.

![](/images/2013-04-16-setting-up-a-custom-domain-on-paperplane/01_empty_dashboard.png)

Think about all those great ideas you have that could be out in the world. Maybe they're even locked up in a Dropbox folder somewhere, but you haven't found the right way to share them. Well, there's no time like the present!

If you click the + in the top-right corner, you should see this little guy (after a totally rad animation!):

![](/images/2013-04-16-setting-up-a-custom-domain-on-paperplane/02_new_site.png)

Aw man, custom domains are grayed out? What's up with that?

Instead of making you track the number of sites you have or the amount of bandwidth you're using (what's a gigabit anyway?), we decided that custom domains probably represent a step up from side project to real deal. If you have a custom domain, you'll probably be driving traffic to it and trying to nab potential customers, so that's probably the right time to spend some money on your idea.

Once you've decided that $9 is a wonderful deal for such a great service, go ahead and click "Get a premium account!" and fill out the credit card form. We're using [Stripe](https://stripe.com/) for payment processing, which we highly recommend. That also means that we don't store your credit card info -- they do. And they're super-duper-ultra secure. (Sites like [reddit](http://www.reddit.com/), [Forrst](http://forrst.com/posts), and [AppSumo](http://www.appsumo.com/) use them too.)

Assuming you typed all the numbers correctly and the internets worked as expected, you should now be able to create a custom domain. I'll walk you through the process we used to create Equity Steaks.

First, let's go ahead and fill out the new site form:

![](/images/2013-04-16-setting-up-a-custom-domain-on-paperplane/03_new_site_filled.png)

Now it says there should be a new folder in Dropbox at Dropbox > Apps > paperplane.io > www.equitysteaks.com. And sure enough:

![](/images/2013-04-16-setting-up-a-custom-domain-on-paperplane/04_dropbox_folder.png)

There it is.

There's also some gobbledygook at the bottom about CNAME DNS WTFBBQ. If you're not familiar with domain hosting, it can be kind of a bear. If you've ever used GoDaddy, you might think it's the hardest process in the world. Luckily, there's some new domain registrars that make the process much simpler. I use [iwantmyname](https://iwantmyname.com/) to do all of my hosting, so I'll show you how to setup your domain there. ([DNSimple](https://dnsimple.com/) is another good one if you want to compare.)

First, search for your preferred domain name using their simple search tool:

![](/images/2013-04-16-setting-up-a-custom-domain-on-paperplane/05_iwantmyname_search.png)

(In my case, equitysteaks.com is taken because I already own it.)

Once you've found a domain name that you like that's available, go ahead and add it to your cart and check out. After completing the purchase, go to your dashboard:

![](/images/2013-04-16-setting-up-a-custom-domain-on-paperplane/06_iwantmyname_dashboard.png)

Select "Manage DNS Records" from the Manual DNS section.

You should see a list of the domains you own. Here's what mine looks like:

![](/images/2013-04-16-setting-up-a-custom-domain-on-paperplane/07_iwantmyname_sites.png)

We're going to be changing equitysteaks.com, so I'll click on "Edit DNS Records" on that row.

We only need two records to get our site up and running: an A-record and a CNAME.

First, add a record with hostname `www`, type `CNAME`, and value `proxy.paperplane.io`. Go ahead and leave the TTL blank -- it defaults to 3600 seconds, which is 1 hour. That means that domain changes might take up to one hour to take effect, depending on your internet provider.

Now, if someone visits www.equitysteaks.com, paperplane will automatically serve your site out of Dropbox. Pretty neat, huh?

What happens if someone visits equitysteaks.com, without the www?

![](/images/2013-04-16-setting-up-a-custom-domain-on-paperplane/08_no_a_record.png)

WHOOPS! That's no good. We need to add something called an A-record. If I want my site to show up in the browser bar as equitysteaks.com (without the www), I'll need to jump through some hurdles and find IP addresses and generally do messy things. That sounds hard, and this is supposed to be easy, right?

Instead, let's use a service called [WWWizer](http://wwwizer.com/naked-domain-redirect) to do a "naked domain redirect." The tl;dr version for iwantmyname: Add a new DNS record. Leave the hostname blank, set the type to `A`, and set the value to 174.129.25.170. This IP address is run by WWWizer, and all it does is redirect from equitysteaks.com to www.equitysteaks.com. (Some other registrars, like DNSimple, have something called a [301 Redirect](https://dnsimple.com/url-forwarding-301-redirect) that can be used to accomplish the same thing.)

Once you're done, the two records should look like this:

![](/images/2013-04-16-setting-up-a-custom-domain-on-paperplane/09_iwantmyname_records.png)

Now we play the waiting game. If your ISP is Super Great&trade;, you should be able to go to visit your custom domain within a few seconds and see the right content. It might take up to an hour, though. If it takes more than an hour, [send us an email](mailto:paperplane@fivedayprototype.com) and we'll help you debug.

Phew! We made it. Your new project/product/portfolio/other-cool-idea-you-should-tell-us-about is live on the internet with a custom domain. Once you get the hang of your domain registrar, you should be able to take any HTML + CSS + JavaScript site you have on your computer and ship it within minutes.

When you're launching a new product, anything that gets in your way can sap momentum, which can kill new ideas. Tools like paperplane take the pain out of shipping new things and make hosting fun again.