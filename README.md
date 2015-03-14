# Source of the gitted.io website

* See the live website at: http://gitted.io/

* To deploy the website using Sysconf, *check out the
  [sysconf/master](https://github.com/sysconf/gitted.gitted-io/tree/sysconf/master)
  branch*

This *Git repository* is also a *Gitted repository* which, together
with the
[_sysconf/master_ branch](https://github.com/sysconf/gitted.gitted-io/tree/sysconf/master),
embeds the full definition of the gitted.io website server.

The official upstream repository is hosted on GitHub:
http://github.com/sysconf/gitted.gitted-io


## This _sysconf/master_ branch: machine definition of the website server

* Learn more about Sysconf at: http://gitted.io/sysconf/

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

