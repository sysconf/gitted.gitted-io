## A Sysconf profile

This is a [SYSCONF](https://github.com/geonef/sysconf.base)
profile. SYSCONF is a method and tool to manage custom system files
for easy install, backup and sync.

This profile provides a [Textree](http://redmine.org/) service.
Textree is a Jade-like syntax processor that allows easy writing of
HTML or XML files with auto-templating and Javascript-based scripting
features.

### Documentation

* [How to fix textree formatting](doc/fix-textree-formatting.md)

## Services

```
# netstat -tlpn
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name
tcp        0      0 0.0.0.0:11211           0.0.0.0:*               LISTEN      -               
tcp        0      0 0.0.0.0:80              0.0.0.0:*               LISTEN      6586/nodejs     
tcp6       0      0 :::11211                :::*                    LISTEN      -               
```

* The main service is Textree, running on port 80.
* A [Memcached](http://memcached.org) service is running on port 11211


## Gitted import/export

Textree data is pushed through Git/Gitted (see below "Gitted
integration"), as a directory named *textree*.

* See: [master.textree.import](tree/etc/gitted/master.textree.import)
  responsible to update textree from the external push.

Other import/export provided by dependencies:
* sysconf.gitted [provides import/export](https://github.com/geonef/sysconf.gitted/tree/master/tree/etc/gitted/sync) of the ```sysconf/``` directory



## Gitted integration

* To create a new Gitted repository, follow the instructions at
  [How to setup Gitted for an application](https://github.com/geonef/sysconf.gitted/blob/master/doc/howto-create-new.md)
  
* Then add this Sysconf profile:
```
git subtree add -P sysconf/sysconf.textree git@github.com:geonef/sysconf.textree.git master
```

* Integrate it in the dependency chain, for example:
```
echo sysconf.textree >sysconf/actual/deps
```

* Create textree data in ```textree/root/```

* Commit push it to the container:
```
sysconf/gitted-client register
git push <name> master
```


## Authors

Written by Jean-Francois Gigand <jf@geonef.fr>. Feel free to contact me!
