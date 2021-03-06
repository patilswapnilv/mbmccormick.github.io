---
layout: post
title: Recovering From the WordPress White Screen of Death
date: 2010-11-16 00:00
comments: true
categories: []
---
<p>At some point in your tenure with WordPress, you may be faced with the &ldquo;white screen of death&rdquo; from time to time. Over the weekend I was updating a plugin on this blog and something, somewhere went wrong. WordPress was unresponsive and I couldn&rsquo;t get to my website or the administration panel, it was as if my website never existed. Initially, I was intimidated by the utter size of WordPress and didn&rsquo;t know where to begin debugging this problem. I decided to see if I could disable the plugin that I was trying to upgrade from the backend, in the database. I fired up phpMyAdmin and opened up the <code>wp_options</code> table. I then found a record called <code>active_plugins</code>. Here&rsquo;s an example of my website&rsquo;s <code>option_value</code> cell:</p>

<script src="https://gist.github.com/755764.js"> </script>


<p></p>

<p>I copied the contents of this record&rsquo;s <code>option_value</code> cell to my desktop as a backup. I then deleted the contents of this cell, so that WordPress would disable all plugins on my blog. When I reloaded my website, I was back in business! I then reinstalled the out-dated plugin manually and reactivated my other plugins.</p>
