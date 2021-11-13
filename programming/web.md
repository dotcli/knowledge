# web

> [\#web](https://memex.changbai.li/#tag-web)

## Launch Chrome with flags for local development

Having a shortcut for launching chrome that ignores some security restrictions, is quite useful for development.

### Example: Launch Chrome without CORS

__Windows__

1. Create a new shortcut
2. In the properties of that shortcut, add after `chrome.exe"`: ` --disable-web-security --disable-gpu --user-data-dir=~/chromeTemp`

__OSX__

`open -n -a /Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome --args --user-data-dir="/tmp/chrome_dev_test" --disable-web-security`

__linux__

`google-chrome --disable-web-security`

### Launch Chrome and allow scripts to access local files

`-–allow-file-access-from-files`