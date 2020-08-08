# Shell Commands

## Operating system

Copy files securely: `rsync -auvP <origin> <destination>`

zip: `zip <name.zip> <file to be zipped> `, `zip -r <name.zip> <directory to be zipped> `

unzip: `unzip <.zip> <optional directory to unzip to>`

list: `ls -l` shows detail. `ls -S` sorts by size. `ls <directory>` lets you peek side a directory

check file / folder size: `du -sh <directory_name> `

Print Working Directory: `pws` tells you where you're at

Shutdown: `sudo shutdown -h now`

Restart: `sudo shutdown -r now`

chown: 

chmod: 

## Server Admin

Copy files between local and remote: `scp ~/rebels.txt dvader@deathstar.com:~/revenge`

ssh: `ssh pi@192.168.3.8`

To restart an apache server, so that configs could apply: `sudo service apache2 restart`

To apply config for NGINX: `service nginx reload`

or on Windows: `nginx -s reload`

## Media

Convert between media formats: `ffmpeg -i <input> <output>`

Bulk convert avi to mp4: `for i in *.avi; do ffmpeg -i "$i" "${i%.*}.mp4"; done`

Generate gif from video:

```
ffmpeg -ss <start second> -t <capture length in second> -i <video file> -vf "fps=20,scale=640:-1:flags=lanczos,split[s0][s1];[s0]palettegen[p];[s1][p]paletteuse" -loop 0 output.gif
```
This captures a 20 fps gif of 640 width (height is auto, preserving aspect ratio). `-ss` for starting second, `-t` for length of gif in second.

# Tricks

### Alert you when a long task is finished

You can make commands execute one after another with `&&`. For example, `cd project && git status` would change directory to the `project` folder, then display git repo status. A cool way to use this is to alert you when a long-running process has finished, by chaining something like `printf \\a` (print a "bell" character, which makes the computer beep), or `say "Process finished."` (this only works on mac).

There's also `||` which only executes a command if the previous one fails. For example, `git clone <some huge repo> || say "Download failed"` would alert you if the repo couldn't be downloaded.

Combining these two, you can even make it alert you for either success or failure.

`git clone <repo url> && say "Download successful" || say "Download failed"`

## Other common tasks to add to wiki:

how to reboot linux

how to schedule tasks
