openwrt-rt-feed
===================
OpenWrt packages - mainly for Internet of Things

## How to use this feed ##
Just add it to your feeds.conf file:

    $ echo "src-git rooterkyberian https://github.com/rooterkyberian/openwrt-rt-feed.git" >> feeds.conf

update feed

    $ ./scripts/feeds update rooterkyberian

and install packages from feeds to make them avaiable in menuconfig

    $ ./scripts/feeds install -a

