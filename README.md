KORUZA OpenWrt Package Feed
===========================

This is an OpenWrt package feed containing KORUZA-related packages.

To use these packages, add the following line to the `feeds.conf`
in the OpenWrt buildroot:
```
src-git koruza https://github.com/IRNAS/koruza-openwrt-packages.git
```

Update the feed:
```
./scripts/feeds update koruza
```

Activate the package:
```
./scripts/feeds install -a -p koruza
```

The KORUZA packages should now appear in menuconfig.

