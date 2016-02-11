![Engintron](https://engintron.com/assets/logo/Engintron_Logo_316x98_24_black.png) **(v1.5.2 - released Feb 7th, 2016 - [See CHANGELOG](#changelog))**
***

##### [Engintron.com](https://engintron.com) | [FAQ](#faq) | [Documentation (Wiki)](https://github.com/engintron/engintron/wiki) | [Issues (for support requests & bug reports)](https://github.com/engintron/engintron/issues) | [Engintron on cPanel Applications Directory](https://applications.cpanel.com/listings/view/Engintron-Nginx-on-cPanel)
***

_Engintron for cPanel/WHM is the easiest way to integrate Nginx on your cPanel/WHM server. Engintron will improve the performance & web serving capacity of your server, while reducing CPU/RAM load at the same time. It does that by installing & configuring the popular Nginx webserver to act as a reverse caching proxy for static files (like CSS, JS, images etc.) with an additional micro-cache layer to significantly improve performance of dynamic content generated by CMSs like WordPress, Joomla or Drupal as well as forum software like vBulletin, phpBB, SMF or e-commerce solutions like Magento, OpenCart, PrestaShop and others._

![Engintron v1.5.x](https://engintron.com/assets/screenshots/1.5.0_20160203.png)


==
### Engintron is Nginx on cPanel

Nginx® is a powerful open source web server that was built to scale websites to millions of visitors. cPanel® is the leading hosting control panel worldwide.

Engintron integrates Nginx into cPanel so you can enjoy amazing performance for your sites, without having to sacrifice important hosting features found in cPanel.

_And best of all? Engintron is totally free to use!_


### But why should you use Nginx in your cPanel server?

cPanel uses the Apache webserver to serve websites by default. Apache however is not known to perform well under heavy web traffic (especially traffic spikes) and it's also CPU/RAM hungry. So how can you mitigate these issues? The answer is simple: by deploying Nginx, another popular web server software, in front of Apache. Nginx acts as a web traffic proxy, directly serving all static assets like CSS, JS, images etc. by default, instead of Apache. This drops significantly the CPU/RAM resources consumed by Apache, leaving your server with more available resources for other tasks or, better still, with room for more websites to host.

The way Engintron sets up Nginx inside your cPanel is a lot like how the popular CloudFlare CDN works. Nginx (like CloudFlare) directly serves all static content like CSS, JS, images etc. instead of your actual web server, thus lowering the load on your cPanel server. But unlike CloudFlare which requires that all your domains are set up with that service, you do everything inside your cPanel server. And better still? You can also have an additional caching layer for when your traffic spikes, not just on one website, but entirely for your server. This additional caching layer is referred to as a "micro cache" and it only caches GET & HEAD requests (never POST requests) which means that it is possible to use it on any type of website, either a small dynamic Joomla corporate website or WordPress blog to a more complex news portal or forum or e-commerce website, that requires users to log in and handle personalized content or even generate content. Engintron's 1 second "micro cache" solution setup with Nginx is therefore ideal for any type of website and it can raise the number of concurrent requests served by your cPanel server from a few hundred per second (using just Apache) to thousands (using Nginx in front of Apache).

Not only will your serving capacity increase, but the load on your server will also significantly drop :)

If you are facing performance issues with your cPanel server, Engintron is your go-to solution. And in fact it's really a "set & forget" solution as you'll set it up once and then it will just run on your server without any additional maintenance on your side.

If you can sign up for a cPanel/WHM server on any hosting company and work your way through WHM, then setting up Engintron should be a piece of cake for you. If you don't manage your cPanel server, then you can always (kindly) ask your hosting company or system administrator to have a look at Engintron and deploy it on your cPanel server. It really only takes a few minutes and there is zero configuration afterwards to get the standard optimizations offered by Nginx.


### OK, I'm sold! How do I install Engintron on my cPanel server?

Installation is a process that lasts only a few minutes. You'll need root SSH access to your cPanel server. Also check the current requirements (listed lower). If everything is ok, log in as root and type the following commands, one at a time:

_$ cd /  
$ rm -f engintron.sh  
$ wget [https://raw.githubusercontent.com/engintron/engintron/master/engintron.sh](https://raw.githubusercontent.com/engintron/engintron/master/engintron.sh)  
$ bash engintron.sh install_

The process will take a couple of minutes to complete and after that, Engintron will be installed on your cPanel server. Engintron has a nice user interface which is activated inside WHM, under the Plugins section. After installation, refresh WHM in your browser and you should see Engintron in the Plugins section (it's the absolute last section in WHM's sidebar).

In there, you'll find basic options to control Nginx, Apache and MySQL, all in one convenient place. Additionally, you can edit all of Nginx's configuration files (as well as some from Apache & MySQL) to get even more from Engintron (like enabling the micro-cache). If however all you want is to accelerate static content delivery, then Engintron is already setup for you and you don't need to do anything more.

Inside the Engintron app dashboard you'll also find some handy utilities to monitor things like your Nginx access & error logs, check processes on your server or see incoming traffic on port 80.

_For more information regarding setup, configuration or uninstallation, as well as other cPanel optimization tips, please visit the project's Wiki pages at: [https://github.com/engintron/engintron/wiki](https://github.com/engintron/engintron/wiki)_


### Why is Engintron a better solution compared to other Nginx installers for cPanel

There are 8 key differences when comparing Engintron with other Nginx installers for cPanel.

First and foremost, caching actually works with Engintron. It works as it should and it works universally. You install it, enable micro-caching (this setting will be enabled by default after v1.5.3 is released) and ALL your cPanel websites will get accelerated, even the slowest ones. Not only that, your serving capacity will increase tremendously. Simple Apache Benchmark (ab) tests reveal a phenomenal increase in concurrent requests served per second, from just 3-300 in Apache to 15,000-20,000 or even more using Nginx via Engintron. It's our carefully crafted "black box" configuration that does all the magic. And it requires literally almost zero maintenance.

Second, Engintron is a single shell script (weighing only a few KBs) that installs all required software (to make Nginx work as intended) from the official software package vendors' repositories. Both installation and updates are very fast (they take only a few seconds).

Third, since we're using the official repositories for Nginx, all Engintron software is updated whenever cPanel (or the server's software) is updated. So you essentially set it and forget it. Whenever you perform "yum update/upgrade" or upgrade the server software from within WHM, Nginx will be updated if a new release is available. If something is changed on Engintron and you need to re-install it, you simply install it on top of the previous installation. You don't need to uninstall it first like other Nginx installer plugins for cPanel do! Oh, and it works from CentOS 5 up to CentOS 7.

Fourth, you can safely uninstall Engintron and it will *revert* your entire system to how it was before you installed Engintron. Simple as that. Which means you can try Engintron and if you don't like it or you find it doesn't fit your needs, you can simply uninstall it. Your system will revert to how it was before. Period.

Fifth, it has an amazingly simple yet practical app dashboard inside WHM with all the basic controls for Nginx, Apache, MySQL, the option to edit all important configuration files for these 3 services and even some handy utilities that make Engintron the dashboard in cPanel for your day-to-day sysadmin tasks. Think of it as your cPanel server's mission control. And did we mention you can easily update Engintron from within WHM?

Sixth, it's CloudFlare friendly. Because both CloudFlare and Engintron use Nginx as a reverse caching proxy, unless we configure Nginx in cPanel to properly act as the secondary proxy (after CloudFlare of course), chances are that CloudFlare will freak out and serve your sites with 10xx errors. So, if you have any domains hosted on your cPanel server that use CloudFlare for their CDN, you can simply uncomment a few lines from the "proxy_params_common" Nginx configuration file (the file is commented for your help) and just restart Nginx for the changes to take effect. All this is done entirely inside WHM of course. If additionally you use CloudFlare's SSL, by choosing "flexible SSL" in CloudFlare's dashboard you can direct HTTPS traffic to your cPanel's HTTP port (=Nginx) thus further improving web serving over HTTPS as well. A true win-win situation.

Seventh, it doesn't require Nginx/Apache vhost synchronization when adding new domains via cPanel. That's why you essentially "set it and forget it". Have a look at the other Nginx installers... 'Nough said ;)

And finally, Engintron is 100% open source. You can tear it apart, customize it, fork it, knife it or contribute back to its development. Do whatever you want with it :)


==

### FAQ

Q. How do I get started?
A. Installation is pretty straightforward as you may have read above already. There is however extensive documentation available in the wiki: https://github.com/engintron/engintron/wiki - we even include general optimization guides for your cPanel server!

Q. Engintron is awesome! But I have a problem or I want to report a bug! Where do I do that?
A. The "Issues" section here on GitHub - https://github.com/engintron/engintron/issues - is the right place to report bugs or request for help. We will eventually offer a dedicated support forum when we launch the new Engintron website in Q1 2016.

Q. I have dozens of .htaccess rules in Apache. Will I have to re-write those for Nginx?
A. Of course not! Nginx works as a proxy to Apache, it does not operate as the direct webserver to your content. In other words, you just install Engintron and everything in Apache (and your apps or websites) will function as it did before. Nginx requires no maintenance. It just works.

Q. Is Nginx secure? Will my server be protected as it is now with Apache. I already have [name 20 protection solution for cPanel here] installed. Do I have to configure my cPanel/WHM server additionally?
A. Nginx is both reliable and secure. In fact, it can even be used to mitigate attacks on software - see how Nginx can be used to protect vulnerable Joomla 3.x websites for a recently disclosed exploit (CVE): https://www.nginx.com/blog/new-joomla-exploit-cve-2015-8562/ - and when used with micro-caching enabled, it can even handle large DoS (denial of service) attacks by simply doing what it does best: handle huge web traffic! To be more precise, all you need for a secure server is ConfigServer's CSF firewall (essentially a frontend for IPTables) to handle basic firewall functionality for your server and Engintron for web traffic (and the occasional app protection like the above Joomla exploit)

Q. How does Engintron (and Nginx) handle HTTPS traffic?
A. Because of the way SSL certificates are currently setup in cPanel, HTTPS traffic will only go through Apache (for the moment).

Q. Do you plan on having Nginx serve HTTPS traffic in upcoming releases of Engintron?
A. Glad you asked! Let me briefly explain how HTTPS traffic is currently handled in cPanel. First off, if you need to use SSL/TLS certificate for any of your domains, you need to either have a dedicated IP available per domain or pay a more expensive multidomain certificate (called UCC/SAN) to be able to use your shared IP address with multiple domains. In either case, the domains that don't have a dedicated SSL/TLS certificate or are not preconfigured in your UCC/SAN multi-domain certificate will NOT be served at all! Instead, Apache will just redirect any domain called with "https://" to server's IP, which kinda looks bad, right? So how can all this be solved, "the right way"? We are waiting for the new certificate authority [Let's Encrypt](https://letsencrypt.org/) to be publicly available and flagged as "stable" in order to have Engintron configure a UCC/SAN certificate for **ALL** your domains in cPanel. This way you'll be able to switch all your sites to HTTPS traffic and with valid certificates! Not to mention you'll finally skip the embarrassment of having HTTPS traffic for unsupported domains switch to the server's hostname. And if you need exclusions for certain domains, so you can serve certificates from existing authorities like Comodo, Trust, Verisign and others, you'll be able to easily define your exclusions in Engintron's WHM app.

Q. Will it work with CloudFlare?
A. Why yes of course! However you do need to adjust your "proxy_params_common" file a bit (until we automate the process in v1.6 of Engintron or earlier). If you edit this file via WHM, you'll notice there are comments in place for the procedure, so rest assured you got everything you need there. To briefly explain the process, you need to set your server's shared (main) IP and comment 1 line and uncomment 3 more (all documented in the file). If you can't see visitor IPs in your Apache logs, you'll also need to execute a single line command via the terminal as root user. As a sidenote, let me add that if you use CloudFlare for all your cPanel domains, you can essentially have HTTPS traffic for all your domains by switching CloudFlare's "Crypto" settings to "Flexible SSL". This way, CloudFlare's servers will proxy your HTTPS traffic to your server's HTTP port (Nginx). In other words, you get to have both amazing serving capacity and SSL/TLS support at the same time.

Q. Does Engintron require a certain CentOS release to work?
A. Engintron is fully compatible with the last 3 major releases of CentOS. That means CentOS versions 5, 6 and 7 are fully supported. CentOS 4 has not been tested with Engintron as cPanel ceased support for CentOS 4 back in 2012.

Q. Does Engintron work in CloudLinux?
Yes. It is fully compatible with CloudLinux versions 6 & 7. Although we haven't yet tested CloudLinux version 5, we assume Engintron will also work with that version since CloudLinux is essentially based off CentOS. And Engintron is fully compatible with CentOS 5.

Q. How popular is Engintron?
A. Version 1.5 which was made available in the early days of February 2016 is by far our most popular release to date. It was installed on more than 300 servers in the first 2 days alone (and still counting at the time of writing - Feb 11th, 2016)!


==

### Compatibility & Requirements

Engintron is fully compatible with CentOS version 5, 6 and 7 on both 32-bit and 64-bit platforms. Additionally, users have already reported a 100% compatibility with CloudLinux versions 6 & 7.

However at the time of writing (Feb 7th, 2016), Engintron is compatible with EasyApache 3 only, as EasyApache 4 is still in beta and there's currently a bug with it that prevents Nginx from installing onto the system.

The cPanel team have promised to fix this pretty soon (you can follow this thread in the cPanel forums: [https://forums.cpanel.net/threads/why-does-easyapache4-block-nginx-installation-using-yum-official-nginx-repos.524241/](https://forums.cpanel.net/threads/why-does-easyapache4-block-nginx-installation-using-yum-official-nginx-repos.524241/))

If this is not resolved soon, we will just have to resort to building Nginx from source in order to support EasyApache 4. This however has the caveat that Nginx will not be updated whenever the system is (automatically) updated by cPanel. In that case, you will simply need to re-run the installer from within WHM whenever a new version of Nginx is available. If we have to resort to this solution, we'll make sure to have an Nginx version update notifier within Engintron's WHM app so you know when to update.


### Documentation

For more information regarding setup, configuration or uninstallation, as well as other cPanel optimization tips, please visit the project's Wiki pages at: https://github.com/engintron/engintron/wiki


### Feedback, bugs, feature requests & rating

Please post your feedback and any issues or feature requests/suggestions in the project's issue tracker at: https://github.com/engintron/engintron/issues

If you use Engintron, please take a moment to post a review and/or rating in the cPanel Applications Directory at: https://applications.cpanel.com/listings/view/Engintron-Nginx-on-cPanel


### I need commercial support - do you offer such services?

If you wish to go the "extra mile" and optimize your cPanel server both through Engintron as well as through other services that directly affect the performance of your cPanel server (MySQL, Apache, PHP, certain system configuration files and more), feel free to use the contact options from within Engintron to get in touch with us.

Or you can simply emails us at: engintron [at] gmail [dot] com


==
### Changelog

_Feb 7th, 2016 - v1.5.2_

*   Added CentOS 7 support (installer worked fine since 1.5.0, however a few controls in the WHM app did not output the correct messages)
*   Added option to update or re-install Engintron from within the WHM app dashboard

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
Copyright &copy; 2010-2016 [Nuevvo Webware P.C.](http://nuevvo.com)
