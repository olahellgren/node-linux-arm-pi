# node-linux-arm-pi
Since [nodejs.org](http://www.nodejs.org) seems to have discontinued their arm-pi builds I'll be putting my builds here for easy access.

Use `wget raw` to download the file you need. Thrn run the commands below.

```
sudo su -
cd /opt
wget http://nodejs.org/dist/v0.10.25/node-vN.NN.N-linux-arm-pi.tar.gz
tar xvzf node-vN.NN.N-linux-arm-pi.tar.gz
ln -s node-vN.NN.N-linux-arm-pi node
chmod a+rw /opt/node/lib/node_modules
chmod a+rw /opt/node/bin
echo 'PATH=$PATH:/opt/node/bin' > /etc/profile.d/node.sh
^D
```
^D is for Ctrl+D, to exit as superuser

It's not recommended to run node as `root`, you should change owner of the directory

`sudo chown your_user:your_user -R node`

`npm install -g node-gyp` (needed for some plugins)