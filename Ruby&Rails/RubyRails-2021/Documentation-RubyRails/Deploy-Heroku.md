# Docs Rails 2021



#### Deploy Heroku.com

**Error**

```
remote:  !     Failed to install gems via Bundler.
```

**Solution**

```
remote:        Your bundle only supports platforms ["x86_64-darwin-16"] but your local platform
remote:        is x86_64-linux. Add the current platform to the lockfile with `bundle loc
remote:        --add-platform x86_64-linux` and try again.
```

Cek in your gemfile.loc :

```
PLATFORMS
  x86_64-darwin-16
```

Do commandline :
```
bundle loc --add-platform x86_64-linux

// Will add gemfile.loc
PLATFORMS
  x86_64-darwin-16
  x86_64-linux
  
// then
git add .
git commit -m "..."
git push heroku master:main

heroku open
```

My Stackoverflow : https://stackoverflow.com/questions/4574176/heroku-push-rejected-failed-to-install-gems-via-bundler/66758121#66758121

