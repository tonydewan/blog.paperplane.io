---
author: Kyle Shipley
layout: post
title: 3 Simple Tips to Make Your Site Faster
---

<div class="full-width">
  <img src="/images/2013-11-13-3-simple-tips-to-make-your-site-faster/network_tab.png" alt="Network tab"/>
</div>

You may have noticed the changes we made to Paperplane last week that have significantly improved performance. There were a lot of sites that were taking 2-3 seconds to load that are now under 200 milliseconds. (10x improvement!) Even with these changes, you might notice that the HTML loads quickly, but images slowly paint in or CSS styles don't take effect immediately.

We might be able to help with some of these, but there's some simple things you can do to decrease your loading time and make your visitors happier.

### 1. Don't resize images in CSS

You can probably get away with this in some cases, but resizing images in CSS is a major culprit of slow sites. If you've ever used a content management system (CMS) like WordPress or a service like Shopify, you may have noticed that they make multiple copies of your image for different sizes (small, medium, large, jumbo, thumbnail, and so on).

Let's say you upload a 1MB image file at a 1920x1080 resolution. If you're only going to show that at 480px (1/4 of the width), that file could probably be almost 4 times smaller and download 4 times faster. That means your visitors are waiting 4 times as long for that image to download!

**Tip**: Create exact-size versions of your images depending on where they're going to go on your page.

### 2. Optimize your images

<center>
  <img src="/images/2013-11-13-3-simple-tips-to-make-your-site-faster/image_optim.png" alt="ImageOptim"/>
</center>

If you're a photographer, you probably know that images taken with a digital camera have lots of "metadata" (that's data about data) in them. These bits of metadata tell you things like who took the picture, where it was taken, what camera settings were used, and so on. These are great if you're uploading a photo to Flickr or Picasa, but not so great for most web sites. Does your visitor really care what photo settings were used to make your splash image, or do they just want to see your blog or your product?

Luckily, there are some simple tools you can use to shrink your image sizes even further before you upload them to Paperplane. On Mac, I use [ImageOptim](http://imageoptim.com/), which is a simple drag-and-drop compressor and metadata remover. It's almost impossible to explain how simple it is, so just download it and try it out! (Warning: ImageOptim modifies your images in-place, so you might want to make a copy before you use it.)

I haven't used an image optimizer on Windows, but there's some recommendations [here](http://stackoverflow.com/a/16590999/182584) and [here](http://sixrevisions.com/tools/8-excellent-tools-for-optimizing-your-images/). Let us know if you have a favorite!

**Tip**: Use an image optimizer like [ImageOptim](http://imageoptim.com/) to compress images and remove metadata before uploading your images.

### 3. Move JavaScript tags to the bottom of the page

<center>
  <img src="/images/2013-11-13-3-simple-tips-to-make-your-site-faster/javascript_footer.png" alt="JavaScript in the footer"/>
</center>

Browsers have a limit on the number of assets (CSS, JavaScript, images, etc.) they can download from one host at a given time. Although I couldn't find a canonical source, it looks like [this number is 6](http://stackoverflow.com/questions/985431/max-parallel-http-connections-in-a-browser) for most modern browsers. If you're loading a lot of JavaScript files, especially big ones, they might prevent images or CSS styles from loading. Your visitors probably need a moment to read your page and understand what they're looking at, so the interactive bits of your website can probably wait a few milliseconds.

One solution to this problem is minification. Basically, you can write some code or use a tool that will smash all your JavaScript together, shorten variable names to single letters, and sometimes even zip the output. This is great because your file is smaller and only requires one connection to download. On the flip side, it's kind of hard. I might talk about minification tools in a future post, but there's a simpler option for now.

The simpler approach is simply moving JavaScript tags to the footer of your page. Browsers kick off downloads in the order they see them. If your JavaScript is all the way at the bottom, that means your browser has already started downloading all of the CSS styles and images on your page. The page loads quickly, your visitors read your content, and they don't even realize that if they had clicked on an element 10ms after your page loaded, it wouldn't have had that cool JavaScript behavior you wrote.

### Speed doesn't have to be hard!

Optimizing performance can be really difficult. If you need Google levels of speed, it might take you 20 engineers and 2 years to shave 50ms off of a request. But when you're first getting started with web development and design, there's almost always a few small things you can do that will provide you with the best outcomes for the least effort. If you can spend 20% of the time to get 80% of the benefit, take that trade every time!

If you enjoyed these tips, want to know more about speeding up your site, or are having any trouble with Paperplane, let us know at [support@paperplane.io](mailto:support@paperplane.io) or on [Twitter](https://twitter.com/paperplaneio).