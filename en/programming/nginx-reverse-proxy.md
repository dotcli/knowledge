# Setting up HTTPS web servers

By using NGINX reverse proxy, you can turn any shitty experimental server into a full-fledge production-level HTTPS super secure web service.

(not really. But this method does provide port 80 access and easily add HTTPS to any web server.)

Example: nodejs app kept running via `pm2`, on a __Tencent Cloud__ _Ubuntu 18.04 LTS_ server.

### Install nginx

```
sudo apt install nginx -y
```

### set up pm2 to keep running the nodejs app

Check their docs. Use it with systemd via `pm2 startup` to run at startup.

##### Key commands:

```bash
pm2 start app.js
pm2 list
pm2 startup systemd
pm2 save
pm2 kill
sudo systemctl start pm2-${username}.service
systemctl status pm2-${username}.service
```

### set up nginx

Use this https://www.digitalocean.com/community/tutorials/how-to-set-up-a-node-js-application-for-production-on-ubuntu-18-04 tutorial. Check the prerequisite part for how to write a sites-available file. Check the last example config for SSL ability.

For tencent cloud, the `ufw` was disabled, so I got to skip that part of the tutorial.

```bash
# First, write the config file under /etc/nginx/sites-available/sitename
blablabla...
# link the config file to sites-enabled
sudo ln -s /etc/nginx/sites-available/sitename /etc/nginx/sites-enabled/

# use this to check if config file format is correct
sudo nginx -t
# apply the new config
sudo service nginx reload
# this command also applies the new config
sudo systemctl restart nginx
```

