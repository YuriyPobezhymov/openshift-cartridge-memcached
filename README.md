# OpenShift Memcached Cartridge

This is modification of the original `memcached` cartridge provides [Memcached](http://www.memcached.org/) on OpenShift, to install  create your app and run:

	rhc add-cartridge "https://raw.githubusercontent.com/YuriyPobezhymov/openshift-cartridge-memcached/master/metadata/manifest.yml" -a [APP]

It has some small changes to work with Red Hat OpenShift Online. The cartridge purpose to be used with PHP client [memcache](https://pecl.php.net/package/memcache), that is installed when PHP application (I use PHP 5.4 cartridge for that) created with Red Hat OpenShift Online.
Memcached system version is the most recent.

## Environment Variables

The `memcached` cartridge provides following environment variables:

    OPENSHIFT_MEMCACHED_HOST         The Memcached IP address
    OPENSHIFT_MEMCACHED_PORT         The Memcached port
    OPENSHIFT_MEMCACHED_USERNAME     Username (if auth enabled)
    OPENSHIFT_MEMCACHED_PASSWORD     Password (if auth enabled)
    
SASL support disabled.

To setup how much memory memcached is allowed to use by settings user env var MEMCACHED_CACHESIZE:

    rhc set-env MEMCACHED_CACHESIZE=128 --app $OPENSHIFT_APP_NAME"
    rhc app-restart --app $OPENSHIFT_APP_NAME"
