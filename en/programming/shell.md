# Shell Commands

Copy files between local and remote: `scp ~/rebels.txt dvader@deathstar.com:~/revenge`

ssh: `ssh pi@192.168.3.8`

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

To restart an apache server, so that configs could apply: `sudo service apache2 restart`

To apply config for NGINX: `service nginx reload`

or on Windows: `nginx -s reload`

## Other common tasks to add to wiki:

how to reboot linux

how to schedule tasks
