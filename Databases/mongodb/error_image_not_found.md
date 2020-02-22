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

It works! ;)



