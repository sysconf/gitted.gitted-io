# Source of the gitted.io website

* See the live website at: http://gitted.io/

* Check out the textree website content by switching to the
  *[textree](https://github.com/sysconf/gitted.gitted-io/tree/textree)
  branch*

This *Git repository* is also a *Gitted repository* which embeds the
full definition of the [gitted.io](http://gitted.io/) website server
using 2 branches:

* _[sysconf/master](https://github.com/sysconf/gitted.gitted-io/tree/sysconf/master)_
  for the Sysconf definition of the website server

* _[textree](https://github.com/sysconf/gitted.gitted-io/tree/textree)_
  for the website content, powered by the
  [textree text processor](https://github.com/geonef/sysconf.textree/)
  to render into HTML.


The official upstream repository is hosted on GitHub:
http://github.com/sysconf/gitted.gitted-io


## This _sysconf/master_ branch: machine definition of the website server

* Learn more about Sysconf at: http://gitted.io/sysconf/

## How to deploy on a local LXC container

You may need to ```apt-get install git lxc``` if not present on your
system already. Then run, as an priviledged user:
```
git https://github.com/sysconf/gitted.gitted-io.git && cd gitted.gitted-io
./gitted-target init lxc:gitted-io
git push gitted-io sysconf/master textree
```

That's all. Get the container IP address with ```lxc-ls -f``` then open
a browser tab to ```http://<ip>```.

### How to deploy on a SSH server

Same as before, but replace ```lxc:gitted-io``` with
```ssh:USER@HOST```, replacing USER@HOST with you case (SSH host
aliases are allowed, like ```ssh:HOSTNAME```).


## Maintenance

### Git subtrees

To update the different Sysconf layers from their GitHub upstream:
```
git subtree pull -P sysconf.base git@github.com:geonef/sysconf.base.git master
git subtree pull -P sysconf.gitted git@github.com:geonef/sysconf.gitted.git master
git subtree pull -P sysconf.textree git@github.com:geonef/sysconf.textree.git master
```

To push updated of the different Sysconf layers to their GitHub upstream:
```
git subtree push -P sysconf.base git@github.com:geonef/sysconf.base.git master
git subtree push -P sysconf.gitted git@github.com:geonef/sysconf.gitted.git master
git subtree push -P sysconf.textree git@github.com:geonef/sysconf.textree.git master
```

## Authors & history

* By JF Gigand <jf@geonef.fr>. Deployed on 20150314 to http://gitted.io/

