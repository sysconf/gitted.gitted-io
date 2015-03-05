# /sysconf repository of the gitted.io website

* See it live at: http://gitted.io/


## Git subtrees

git subtree push -P sysconf.base git@github.com:geonef/sysconf.base.git master
git subtree push -P sysconf.gitted git@github.com:geonef/sysconf.gitted.git master
git subtree push -P sysconf.textree git@github.com:geonef/sysconf.textree.git master

git subtree pull -P sysconf.base git@github.com:geonef/sysconf.base.git master
git subtree pull -P sysconf.gitted git@github.com:geonef/sysconf.gitted.git master
git subtree pull -P sysconf.textree git@github.com:geonef/sysconf.textree.git master
