

UPDATE 1 APRIL 2021

(base) dyo-mac:~ dyo-medio$ mongod
dyld: Library not loaded: /usr/local/opt/openssl/lib/libssl.1.0.0.dylib
  Referenced from: /usr/local/bin/mongod
  Reason: image not found

PROBLEM adalah 

Tidak ditemukan folder openssl di my computer.











```
dyld: Library not loaded: /usr/local/opt/openssl/lib/libssl.1.0.0.dylib
  Referenced from: /usr/local/bin/mongod
  Reason: image not found
Trace/BPT trap: 5
```



Try:

https://github.com/kelaberetiv/TagUI/issues/86

```
brew update && brew upgrade

brew uninstall openssl; brew uninstall openssl; brew install https://github.com/tebelorg/Tump/releases/download/v1.0.0/openssl.rb
```

```
You can override this and force removal with:
  brew uninstall --ignore-dependencies openssl
Error: Refusing to uninstall /usr/local/Cellar/openssl@1.1/1.1.1j
because it is required by cocoapods, docker-compose, glib, gnupg, gnutls, imagemagick, itstool, krb5, libevent, libheif, liblqr, libssh2, meson, mysql, nghttp2, ninja, postgresql, python@2, python@3.8, python@3.9, ruby, rust, shared-mime-info, sphinx-doc, tcl-tk, unbound, watchman and wget, which are currently installed.
You can override this and force removal with:
```



I do 


```
brew uninstall --ignore-dependencies openssl
```

and

```
Warning: The following openssl@1.1 configuration files have not been removed!
If desired, remove them manually with `rm -rf`:
  /usr/local/etc/openssl@1.1
  /usr/local/etc/openssl@1.1/cert.pem
  /usr/local/etc/openssl@1.1/certs
  /usr/local/etc/openssl@1.1/ct_log_list.cnf
  /usr/local/etc/openssl@1.1/ct_log_list.cnf.dist
  /usr/local/etc/openssl@1.1/misc
  /usr/local/etc/openssl@1.1/misc/CA.pl
  /usr/local/etc/openssl@1.1/misc/tsget
  /usr/local/etc/openssl@1.1/misc/tsget.pl
  /usr/local/etc/openssl@1.1/openssl.cnf
  /usr/local/etc/openssl@1.1/openssl.cnf.dist
  /usr/local/etc/openssl@1.1/private
```

and remove manualy

```
rm -rf /usr/local/etc/openssl
```

and do 

```
brew install https://github.com/tebelorg/Tump/releases/download/v1.0.0/openssl.rb
```







### This not Works anymore!

```
# PROBLEM

dyld: Library not loaded: /usr/local/opt/openssl/lib/libssl.1.0.0.dylib
```

```
# SOLUTION

first, list the details of the installed openssl version(or other programs) by:

ls -al /usr/local/Cellar/openssl*

/usr/local/Cellar/openssl:
total 0
drwxr-xr-x    3 mba  staff    96 Nov 30 17:18 .
drwxrwxr-x  170 mba  admin  5440 Apr  8 02:03 ..
drwxr-xr-x   13 mba  staff   416 Nov 21 03:13 1.0.2t

/usr/local/Cellar/openssl@1.1:
total 0
drwxr-xr-x    4 mba  staff   128 Apr  7 18:35 .
drwxrwxr-x  170 mba  admin  5440 Apr  8 02:03 ..
drwxr-xr-x   14 mba  staff   448 Oct  1  2019 1.1.1d
drwxr-xr-x   14 mba  staff   448 Apr  7 18:35 1.1.1f
```

as above output, there are only one "right" versions "openssl" in my mac. then, switch to it:

```
$brew switch openssl 1.0.2t Cleaning /usr/local/Cellar/openssl/1.0.2t
Opt link created for /usr/local/Cellar/openssl/1.0.2t
```

Link: https://stackoverflow.com/questions/59006602/dyld-library-not-loaded-usr-local-opt-openssl-lib-libssl-1-0-0-dylib/61086871#61086871

UPDATE this solution:

Error: Unknown command: switch

I tried to use : brew commands

no command switch now :(

