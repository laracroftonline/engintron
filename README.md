![Engintron](https://engintron.com/assets/logo/Engintron_Logo_316x98_24_black.png)

**[Engintron v1.7.1 released Aug 19th, 2016 - [See CHANGELOG](#changelog)]**
***

##### Quick Nav: [Engintron.com](https://engintron.com) | [FAQ](#faq) | [Documentation (Wiki)](https://github.com/engintron/engintron/wiki) | [Issues (for support requests & bug reports)](https://github.com/engintron/engintron/issues) | [Engintron on cPanel Applications Directory](https://applications.cpanel.com/listings/view/Engintron-Nginx-on-cPanel) | [Newsletter / Mailing List](https://tinyletter.com/engintron)
***

_Engintron for cPanel/WHM is the easiest way to integrate Nginx on your cPanel/WHM server. Engintron will improve the performance & web serving capacity of your server, while reducing CPU/RAM load at the same time. It does that by installing & configuring the popular Nginx webserver to act as a reverse caching proxy for static files (like CSS, JS, images etc.) with an additional micro-cache layer to significantly improve performance of dynamic content generated by CMSs like WordPress, Joomla or Drupal as well as forum software like vBulletin, phpBB, SMF or e-commerce solutions like Magento, OpenCart, PrestaShop and others._


***
# NEW - Join the Engintron Newsletter / Mailing List
It's easy to miss an Engintron update on social media. If you want to know for sure when the latest version of Engintron is released, sign up to get notified directly to your inbox. We will never spam you.

Sign up here https://tinyletter.com/engintron or here https://engintron.com
***


![Engintron App in WHM](https://engintron.com/assets/screenshots/1.6.0_20160216_ad_2048x1072.png)


==
### Engintron is Nginx on cPanel

Nginx® is a powerful open source web server that was built to scale websites to millions of visitors. cPanel® is the leading hosting control panel worldwide.

Engintron integrates Nginx into cPanel so you can enjoy amazing performance for your sites, without having to sacrifice important hosting features found in cPanel.

_And best of all? Engintron is totally free to use!_


### But why should you use Nginx in your cPanel server?

cPanel uses the Apache webserver to serve websites by default. Apache however is not known to perform well under heavy web traffic (especially traffic spikes) and it's also CPU/RAM hungry. So how can you mitigate these issues? The answer is simple: by deploying Nginx, another popular web server software, in front of Apache. Nginx acts as a web traffic proxy, directly serving all static assets like CSS, JS, images etc. by default, instead of Apache. This drops significantly the CPU/RAM resources consumed by Apache, leaving your server with more available resources for other tasks or, better still, with room for more websites to host.

The way Engintron sets up Nginx inside your cPanel is a lot like how the popular CloudFlare CDN works. Nginx (like CloudFlare) directly serves all static content like CSS, JS, images etc. instead of your actual web server, thus lowering the load on your cPanel server. But unlike CloudFlare which requires that all your domains are set up with that service, you do everything inside your cPanel server. And better still? You also have an additional caching layer for when your traffic spikes, not just on one website, but entirely for your server. This additional caching layer is referred to as a "micro cache" and it only caches GET & HEAD requests (never POST requests) which means that it is possible to use it on any type of website, either a small dynamic Joomla corporate website or WordPress blog to a more complex news portal or forum or e-commerce website, that requires users to log in and handle personalized content or even generate content. Engintron's 1 second "micro cache" solution setup with Nginx is therefore ideal for any type of website and it can raise the number of concurrent requests served by your cPanel server from a few hundred per second (using just Apache) to thousands (using Nginx in front of Apache).

Not only will your serving capacity increase, but the load on your server will also significantly drop :)

If you are facing performance issues with your cPanel server, Engintron is your go-to solution. And in fact it's really a "set & forget" solution as you'll set it up once and then it will just run on your server without any additional maintenance on your side.

If you can sign up for a cPanel/WHM server on any hosting company and work your way through WHM, then setting up Engintron should be a piece of cake for you. If you don't manage your cPanel server, then you can always (kindly) ask your hosting company or system administrator to have a look at Engintron and deploy it on your cPanel server. It really only takes a few minutes and there is zero configuration afterwards to get the standard optimizations offered by Nginx.


### OK, I'm sold! How do I install Engintron on my cPanel server?

Installation is a process that lasts only a few minutes. You'll need root SSH access to your cPanel server. Also check the current requirements (listed lower). If everything is ok, log in as root and type the following commands, one at a time:

    cd /  
    rm -f engintron.sh  
    wget --no-check-certificate https://raw.githubusercontent.com/engintron/engintron/master/engintron.sh  
    bash engintron.sh install

Or in one quick command to paste in the terminal:

    cd /; rm -f engintron.sh; wget --no-check-certificate https://raw.githubusercontent.com/engintron/engintron/master/engintron.sh; bash engintron.sh install

The process will take a couple of minutes to complete and after that, Engintron will be installed on your cPanel server. Engintron has a nice user interface which is activated inside WHM, under the Plugins section. After installation, refresh WHM in your browser and you should see Engintron in the Plugins section (it's the absolute last section in WHM's sidebar).

In there, you'll find basic options to control Nginx, Apache and MySQL, all in one convenient place. Additionally, you can edit all of Nginx's configuration files (as well as some from Apache & MySQL) to get even more from Engintron (e.g. configure Engintron for use with CloudFlare). If however all you want is to accelerate both static & dynamic content delivery, then Engintron is already setup for you and you don't need to do anything more.

Inside the Engintron app dashboard you'll also find some handy utilities to monitor things like your Nginx access & error logs, check processes on your server or see incoming traffic on port 80.

_For more information regarding setup, configuration or uninstallation, as well as other cPanel optimization tips, please visit the project's Wiki pages at: [https://github.com/engintron/engintron/wiki](https://github.com/engintron/engintron/wiki)_


### Why is Engintron a better solution compared to other Nginx installers for cPanel

There are 8 key differences when comparing Engintron with other Nginx installers for cPanel.

First and foremost, caching actually works with Engintron. It works as it should and it works universally. You install it and ALL your cPanel websites will get accelerated, even the slowest ones. Not only that, your serving capacity will increase tremendously. Simple Apache Benchmark (ab) tests reveal a phenomenal increase in concurrent requests served per second, from just 3-300 in Apache to 15,000-20,000 or even more using Nginx via Engintron. It's our carefully crafted "black box" configuration that does all the magic. And it requires literally almost zero maintenance.

Second, Engintron is a single shell script (weighing only a few KBs) that installs all required software (to make Nginx work as intended) from the official software package vendors' repositories. Both installation and updates are very fast (they take only a few seconds).

Third, since we're using the official repositories for Nginx, all Engintron software is updated whenever cPanel (or the server's software) is updated. So you essentially set it and forget it. Whenever you perform "yum update/upgrade" or upgrade the server software from within WHM, Nginx will be updated if a new release is available. If something is changed on Engintron and you need to re-install it, you simply install it on top of the previous installation. You don't need to uninstall it first like other Nginx installer plugins for cPanel do! Oh, and it works from CentOS 5 up to CentOS 7.

Fourth, you can safely uninstall Engintron and it will *revert* your entire system to how it was before you installed Engintron. Simple as that. Which means you can try Engintron and if you don't like it or you find it doesn't fit your needs, you can simply uninstall it. Your system will revert to how it was before. Period.

Fifth, it has an amazingly simple yet practical app dashboard inside WHM with all the basic controls for Nginx, Apache, MySQL, the option to edit all important configuration files for these 3 services and even some handy utilities that make Engintron the dashboard in cPanel for your day-to-day sysadmin tasks. Think of it as your cPanel server's mission control. And did we mention you can easily update Engintron from within WHM? Yeap! You even get update notifications when a new version is available.

Sixth, it's CloudFlare friendly. Because both CloudFlare and Engintron use Nginx as a reverse caching proxy, unless we configure Nginx in cPanel to properly act as the secondary proxy (after CloudFlare of course), chances are that CloudFlare will freak out and serve your sites with 10xx errors. So, if you have any domains hosted on your cPanel server that use CloudFlare for their CDN, you just set your server IPs inside your "custom_rules" Nginx configuration file (the file is commented for your help) and just restart Nginx for the changes to take effect. All this is done entirely inside WHM of course. If additionally you use CloudFlare's SSL, by choosing "Flexible SSL" in CloudFlare's "Crypt" settings you can direct CloudFlare HTTPS traffic to your cPanel's HTTP port served by Nginx, thus further improving web serving over HTTPS as well. A true win-win situation.

Seventh, it doesn't require Nginx/Apache vhost synchronization when adding new domains via cPanel. That's why you essentially "set it and forget it". Have a look at the other Nginx installers... 'Nough said ;)

And finally, Engintron is 100% open source. You can tear it apart, customize it, fork it, knife it or contribute back to its development. Do whatever you want with it :)


==

### FAQ

Q. **How popular is Engintron?**  
A. Version 1.5 (and newer releases) which was made available in the early days of February 2016 is by far our most popular release to date. It was installed on more than 300 servers in the first 2 days alone and at the time of writing (July 20th, 2016) it ***has been deployed into more than 5000 servers in over 100 countries worldwide***! You could say that Engintron is probably the most popular cPanel plugin of its kind. For v1.0 we do not really have metrics but we estimate it's below 1000 deployments. However v1.0 had very limited application as it was primarily targeted for websites with no user-generated content (e.g. media/news portals or high traffic blogs). Engintron v1.5 builds upon the knowledge gathered from v1.0 but it has been completely written from the ground up to support any type of website (even those with user generated content like forums, e-shops etc.) and also be easier to use, with little to no configuration after installation.

Q. **How do I get started?**  
A. Installation is pretty straightforward as you may have read above already. There is however extensive documentation available in the wiki: https://github.com/engintron/engintron/wiki - we even include general optimization guides for your cPanel server!

Q. **Engintron is awesome! But I have a problem or I want to report a bug! Where do I do that?**  
A. The "Issues" section here on GitHub - https://github.com/engintron/engintron/issues - is the right place to report bugs or request for help. We will eventually offer a dedicated support forum when we launch the new Engintron website in Q1 2016.

Q. **I have dozens of .htaccess rules in Apache. Will I have to re-write those for Nginx?**  
A. Of course not! Nginx works as a proxy to Apache, it does not operate as the direct webserver to your content. In other words, you just install Engintron and everything in Apache (and your apps or websites) will function as it did before. Nginx requires no maintenance. It just works.

Q. **Is Nginx secure? Will my server be protected as it is now with Apache. I already have [name 20 protection solution for cPanel here] installed. Do I have to configure my cPanel/WHM server additionally?**  
A. Nginx is both reliable and secure. In fact, it can even be used to mitigate attacks on software - see how Nginx can be used to protect vulnerable Joomla 3.x websites for a recently disclosed exploit (CVE): https://www.nginx.com/blog/new-joomla-exploit-cve-2015-8562/ - and when used with micro-caching enabled, it can even handle large DoS (denial of service) attacks by simply doing what it does best: handle huge web traffic! To be more precise, all you need for a secure server is ConfigServer's CSF firewall (essentially a frontend for IPTables) to handle basic firewall functionality for your server and Engintron for web traffic (and the occasional app protection like the above Joomla exploit)

Q. **How does Engintron (and Nginx) handle HTTPS traffic?**  
A. Because of the way TLS/SSL certificates are currently setup in cPanel, HTTPS traffic will only go through Apache (for the moment). We have plans to add TLS/SSL support in upcoming versions by combining existing certificates installed via cPanel and using LetsEncrypt issued certificates for the domains that don't have a certificate installed via cPanel. This feature will probably come in version 1.8.0 of Engintron.

Q. **Will it work with CloudFlare?**  
A. Why yes of course! However you do need to adjust your "custom_rules" Nginx configuration file a bit. When you edit this file via WHM, you'll notice there are comments in place for the procedure, so rest assured you got everything you need there. To briefly explain the process, you need to set your server's shared (main) IP and/or any additional dedicated IPs matching certain domains (everything is documented with examples in there). If you can't see visitor IPs in your Apache logs, you'll also need to execute a single line command via the terminal as root user (also documented in this file). As a sidenote, let me add that if you use CloudFlare for all your cPanel domains, you can essentially have HTTPS traffic for all your domains by switching CloudFlare's "Crypto" settings to "Flexible SSL". This way, CloudFlare's servers will proxy your HTTPS traffic to your server's HTTP port (Nginx). In other words, you get to have both amazing serving capacity and SSL/TLS support at the same time.

Q. **I have Munin installed on my cPanel server to monitor resources. Does Engintron setup Nginx graphs in Munin as well?**  
A. Absolutely. Have a look at the "Using Engintron" document in our Wiki for a screenshot of the graphs you get for Nginx in Munin. If you install Munin after you first installed Engintron, simply re-install Engintron via WHM and you'll get the Nginx graphs in your newly set Munin installation.

Q. **Does Engintron require a certain CentOS release to work?**  
A. Engintron is fully compatible with the last 3 major releases of CentOS. That means CentOS versions 5, 6 and 7 are fully supported. CentOS 4 has not been tested with Engintron as cPanel ceased support for CentOS 4 back in 2012.

Q. **Does Engintron work in CloudLinux?**  
Yes. It is fully compatible with CloudLinux versions 6 & 7. Although we haven't yet tested CloudLinux version 5, we assume Engintron will also work with that version since CloudLinux is essentially based off CentOS and Engintron is already fully compatible with CentOS 5.


==

### Compatibility & Requirements

Engintron is fully compatible with CentOS version 5, 6 and 7 on both 32-bit and 64-bit platforms. Additionally, users have already reported a 100% compatibility with CloudLinux versions 6 & 7.

Engintron is also compatible with both EasyApache 3 and EasyApache 4 as of version 1.7.0.


### Documentation

For more information regarding setup, configuration or uninstallation, as well as other cPanel optimization tips, please visit the project's Wiki pages at: https://github.com/engintron/engintron/wiki


### Feedback, bugs, feature requests & rating

Please post your feedback and any issues or feature requests/suggestions in the project's issue tracker at: https://github.com/engintron/engintron/issues

If you use Engintron, please take a moment to post a review and/or rating in the cPanel Applications Directory at: https://applications.cpanel.com/listings/view/Engintron-Nginx-on-cPanel


==
### I need commercial support - do you offer such services?

If you wish to go the "extra mile" and optimize your cPanel server both through Engintron as well as through other services that directly affect the performance of your cPanel server (MySQL, Apache, PHP, certain system configuration files and more), feel free to use the contact options from within Engintron to get in touch with us.

Or you can simply emails us at: engintron [at] gmail [dot] com


***
# NEW - Join the Engintron Newsletter / Mailing List
It's easy to miss an Engintron update on social media. If you want to know for sure when the latest version of Engintron is released, sign up to get notified directly to your inbox. We will never spam you.

Sign up here https://tinyletter.com/engintron or here https://engintron.com
***


==
### Changelog

_Aug 19th, 2016 - v1.7.1_

*   Addressed potential security issue where Nginx becomes an open proxy when Engintron is disabled and Nginx is switched to port 8080.
*   The "Enable/Disable Engintron" toggler in the Engintron WHM app will now properly display the target state to switch to, e.g. either "Enable Engintron" or "Disable Engintron".

_Aug 17th, 2016 - v1.7.0_

*   Engintron is now EasyApache 4 compatible.
*   Added option to edit the system's crontab file
*   New CLI options added - explore with "/engintron.sh -h"

_Jul 19th, 2016 - v1.6.2_

*   Protect your cPanel server from the [httpoxy](https://httpoxy.org/) vulnerability with the help of Nginx, by setting the "HTTP Proxy" header to null.
*   Install mod_remoteip using the source file provided from the Engintron repo on GitHub. Many installations previously dealt with failed downloads of that file from the official Apache code repo, which resulted in mod_remoteip not being installed at all and thus Nginx could not pass the visitor's IP back to Apache.
*   Bumped proxy read/send timeouts to 180s from 120s.
*   Fixed IPv6 resolver syntax in nginx.conf.
*   The custom_rules file will not be overridden on Engintron updates.
*   You can switch between Nginx stable and mainline (latest) releases with new options in the WHM app and the Engintron CLI.
*   Nuke cookies for static files for good - added 'proxy_ignore_headers Set-Cookie;' & 'proxy_set_header Cookie "";' alongside 'proxy_hide_header Set-Cookie;'.
*   Switched Nginx status page back to public (by default). When that page was set to private, Munin failed to graph Nginx usage. If you don't use Munin, you can uncomment 2 lines in default.conf if you wish to hide that page. In any case, leaving the Nginx status page open does not pose any security or other issue.
*   Nginx log rotation is updated to 7 days (the default option was 52 days!).
*   Moved SVG file handling in Nginx to the "fonts" block as Chrome uses CORS to decide serving to end users.
*   Fixed Nginx cache/temp folder reporting in CentOS 7 (or other systemd based distros where cPanel works).
*   Code changes to make Engintron utilize the WHM API v1 where possible.

_Feb 19th, 2016 - v1.6.1_

*   Engintron will now (be default) modify Apache's log format to allow for the proper inclusion of a visitor's IP in all systems. The change is merged with Apache's configuration so it's protected if Apache settings are modified via WHM. If you uninstall Engintron, Apache's log format is reverted to its previous state.

_Feb 14th, 2016 - v1.6.0_

*   Introducing new "custom_rules" file (fully editable from within WHM) for you to store any custom Nginx rules or redirects. These include custom setup for CloudFlare or for certain domains. The only thing you need to edit to apply any rules from now on is "custom_rules" and that's why upon updates, we keep a copy of that file and display it within WHM so you can easily copy/paste your custom Nginx rules before the update to the new "custom_rules" file being installed. We could simply keep that file for you, but breaking changes may be introduced so it's always good to be able to keep up to date.
*   CloudFlare integration is now easier than ever. All you have to do is set your shared or any dedicated IPs. We also include some handy redirect rules for CloudFlare, for HTTP to HTTPS. Just uncomment whatever you want to use.
*   Introducing version update checker. If you already have v1.5.3, you'll see the first update notice when you visit Engintron in WHM. Upgrading is as simple as clicking a link in the app.

_Feb 12th, 2016 - v1.5.3_

*   Micro-caching is now enabled by default. Extensive tests have shown that there are no issues caused when micro-caching is enabled. In fact, performance is exponentially increased when micro-caching is on, which is the reason why Engintron now ships with this option on.
*   Improvements to the installer - if any of the Apache modules (RPAF or RemoteIP) fail to install, we just skip that part without causing Apache to stop working because of missing .so files.
*   Increased default timeouts in nginx.conf to minimize 504 errors from slow backends.
*   Added a more reliable way to restart Nginx if another Nginx plugin for cPanel was previously uninstalled leaving Nginx still binding to port 80.

_Feb 7th, 2016 - v1.5.2_

*   Added CentOS 7 support (installer worked fine since 1.5.0, however a few controls in the WHM app did not output the correct messages)
*   Added option to update or re-install Engintron from within WHM, via the Engintron app under "Plugins"

_Feb 6th, 2016 - v1.5.1_

*   General installer/uninstaller improvements
*   Improved compatibility with CentOS 5
*   Added option to enable/disable Engintron without completely uninstalling it. You can control Engintron's state through the WHM app dashboard or via the terminal. Nginx switches to port 8080 and Apache switches to port 80 when you run "$ bash /engintron.sh disable". If you run "$ bash /engintron.sh enable" Nginx reclaims port 80 and Apache takes port 8080.
*   IPv6 support is now present but it has to be uncommented in order to work properly (in files /etc/nginx/nginx.conf for the resolver & /etc/nginx/conf.d/default.conf for the catch-all rule)
*   Improved help/instructions when executing engintron.sh via terminal
*   Added some terminal utilities like "restart Apache & Nginx", "restart all important services", "show server info", "show traffic on port 80" and more. From the terminal type "bash /engintron.sh" or just "/engintron.sh" if you have already installed Engintron.
*   Fixed /nginx_status page - info now also shown under "Nginx Status" option in the WHM app dashboard
*   Fixed /favicon.ico and /robots.txt loading - previously these files were blocked due to a mismatch in their respective definitions
*   Updated retrieval location for mod_rpaf to ensure proper installation on all CentOS releases

_Feb 1st, 2016 - v1.5.0_

*   Complete re-write of the main installer script as well as the app dashboard
*   vhost sync'ing is no longer needed - you add new domains via cPanel and it just works
*   New, smarter, better proxying/caching approach - improves performance without the headaches of controlling exclusions for different CMSs - it just works
*   Proper client side caching for all types of content
*   Compatible with domains served via CloudFlare

_Dec 23rd, 2014 - v1.0.4 Build 20141223_

*   Updated static asset loading from an HTTPS source

_Dec 3rd, 2014 - v1.0.4 Build 20141203_

*   Since mod_rpaf was dropped from its original developer, it's now been updated with the fork that's been actively maintained here: https://github.com/gnif/mod_rpaf
*   Moved all static assets of the app dashboard onto GitHub's CDN. This simply results to a cleaner Engintron script.
*   Removed the line "proxy_hide_header Set-Cookie;" from proxy.conf as it was causing issues with WordPress websites not being properly cached (thank you @AgentGod)

_May 30th, 2014 - v1.0.3_

*   Fixed compatibility with Munin, added Nginx tracking in Munin
*   Enabled access logs for domains, but static file logging is disabled for performance reasons
*   Switched default Nginx worker process to "auto" (aka CPU/core support), so it won't be required to be set manually
*   Obsolete vhosts are now cleaned up whenever the sync process is performed
*   Added some default Nginx files after setup in case they are not created during Nginx's installation
*   Added default.conf vhost during installation

**License**

Engintron is released under the GNU/GPL license. For more info, have a look here: [http://www.gnu.org/copyleft/gpl.html](http://www.gnu.org/copyleft/gpl.html)


==
### More info
A proper website is on its way, featuring short tutorials and videos, a forum and a commercial support channel.

If however you require commercial support now, you can contact us via Engintron's app dashboard or simply email us at: engintron [at] gmail [dot] com

https://engintron.com


==
Copyright &copy; 2014-2016 Fotis Evangelou / [Nuevvo Webware P.C.](http://nuevvo.com)
