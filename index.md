---
layout: page
title: WordPress Developer Documentation
published: true
---

> **Note:** This documentation is primarily intended for [Seravo.com](https://seravo.com) customers. You are can however use our [project structure & Vagrant box](https://github.com/Seravo/wordpress) for any WordPress development no matter where you decide to deploy, host or maintain it. As stated in [LICENSE (MIT)](https://github.com/Seravo/wordpress/blob/master/LICENSE.md), the provides software and documentation is open source and can be used freely anywhere, including also commercial use.

This contains guides and tips for developers who might want to enhance their workflow and use the best modern development tools. Feel free to pick the parts that fit your style of development best!

All Seravo.com sites are preconfigured for optimal development workflow, but the workflow in general or any part of it is not mandatory. You don't have to use Git, Composer or the others if you don't want. Or you can use them, but follow your own workflow. All sites have SFTP/SSH access so all sites support even the most traditional FTP-your-suff-to-the-server-workflow. But if you like the idea of a really optimized workflow, please keep on reading!

This documentation is maintained in a [public git](https://github.com/seravo/docs) repository. If you find any errors or you want to extend the documentation, feel free to contribute!


### Fast-track guide for developing your site:
>**Hint:** Read the other topics to have better understanding what's happening over here. The git repository must be initialized as described in [Local development]({{ site.baseurl }}{% post_url 2015-10-13-local-development %}).

```
# Clone your site to your computer and name the git remote as 'production'
$ git clone ssh://$SSH_USER@$SITE.seravo.com:[$SSH_PORT]/data/wordpress ~/Projects/$SITE --origin production

# (Alternatively clone github.com/Seravo/wordpress and use it as your project template)

# Start developing your site with Vagrant
$ cd ~/Projects/$SITE
$ vagrant up

# Follow the vagrant installer
...

# Make changes to your site
...

# Save your work into git
$ git commit -am "Made some superb changes"

# See if commit triggered tests are succesful
...

# Push your changes to production
$ git push production master
Counting objects: 3, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 317 bytes | 0 bytes/s, done.
Total 3 (delta 2), reused 0 (delta 0)
remote: Seravo: composer.json was updated, installing...
remote: Loading composer repositories with package information
remote: Installing dependencies from lock file
remote: Nothing to install or update
remote: Generating autoload files
remote: > Wordpress\Installer::symlinkWPContent
remote: Seravo: Nginx configs were changed, reloading nginx...
remote: testing nginx configuration...
remote: nginx: the configuration file /etc/nginx/nginx.conf syntax is ok
remote: nginx: configuration file /etc/nginx/nginx.conf test is successful
remote: restarting nginx...
remote: nginx restarted!
To ssh://example@example.seravo.com:12345/data/wordpress/.git
   01b9b80..9b3d006  master -> master

```
