---
layout: post
title:  "Moving site back to Fastmail"
date:   2021-03-12 15:11:00 -0700
categories: blog
author: Nicholas Danes
tags: [blogging, meta]
---

Back in January, I decided to [rehost this website](https://ndanes.com/blog/2021/01/23/moving-site-to-netlify/) with [Netlify](https://netlify.com). Although this has made things incredibly convenient, I sort of didn've love the fact I was relying on GitHub to maintain my website. Ultimately, I decided to move back to the static hosting option using my email provider, [Fastmail](https://fastmail.com).

My complains from before were that only FTP and WebDAV were supported for file transfering when hosting my site with Fastmail. To fix this, I decided to make a simple bash script using [ncftp](https://www.ncftp.com/ncftp/doc/ncftpput.html) to allow push updates to the FTP server without having to use a GUI client. The main command looks something like:


	ncftpput -u $USER -p $PASSWORD -R $HOST $DESTINATION_PATH $ORIGIN_PATH


I stored this command in a bash script called <code>ftp_fastmail_upload</code>. If I was successful, you are reading this blog post from me using that script!

To utilize the FTP script for a one CLI command deploy, I use the following set of aliases:

	# alias to build jekyll site under _site
	alias jb="bundle exec jekyll build"
	# alias which calls a script to upload files to Fastmail server from _site
	alias fm_ftp="bash /home/ndanes/scripts/ftp_fastmail_upload"
	# alias which combines the two aliases above
	alias deploy_site="jb && fm_ftp"


Now that I can deploy my site without using GitHub, I'm considering moving my website repo elsewhere. I may go back to [Codeberg](https://codeberg.org), but ultimately I haven't decided.
