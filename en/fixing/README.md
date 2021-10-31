# Fixing things

## General

### Look it up

When something broke and you don't know how to fix it, first look it up on the web.
Even when it doesn't give you enough guidance on fixing it, you would know more about how to bring it to a professional.

### Search the user group

For software products, search the FAQ & user group. Look for mailing lists, forums (e.g. reddit), other places where users discuss.

If it's an open soure project on Github, check the issues. Leverage the filter.

## Windows 10

### WLAN option disappeared from Network Settings
> Note: The cause may be different for yours. I ran into this problem at Windows 10.0.17134, on an MSI GT62VR laptop.

__Method 1__: Close the laptop lid to put computer to sleep, and open it up again. This seems to trigger some MSI device management behavior and re-detect the network card.

__Method 2__: Change the power saving mode for your wireless adapter, then power cycle the computer. To do this:

1. Go to Settings > System > Power & Sleep > Additional Power Settings > Change Plan settings > Change advanced power settings
2. Under Wireless Adapter Settings > Power Saving Mode, change the setting. What setting you change to don't matter, so long as they are different from what you currently have.
3. Restart the computer.

## Git

### fatal: unable to access 'https://github.com/xxx': OpenSSL SSL_connect: SSL_ERROR_SYSCALL in connection to github.com:443

This error occured to me on both MacOS and Windows when I was using git in China. It seems to be related to the GFW, http proxies, or ipv6, but the cause is unclear.

On mac, see this Zhihu answer [Failed to connect to raw.githubusercontent.com:443
](https://zhuanlan.zhihu.com/p/115450863). 

```
# 7890 和 789 需要换成你自己的端口
export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:789
```

Connecting to git via ssh instead of https also works, but only when you have the option to change remote address. Not for homebrew.

On Windows, I fixed it _somehow_ by running `git init`again in the repo. This does not init an empty repo, but rather rebuilds things in the `.git` folder. Worked like a charm - it works well, but I have no idea what exactly made it work.