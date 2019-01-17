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