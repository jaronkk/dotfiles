## 1. Run thoughtbot laptop setup script

https://github.com/thoughtbot/laptop
```sh
curl --remote-name https://raw.githubusercontent.com/thoughtbot/laptop/master/mac
less mac
sh mac 2>&1 | tee ~/laptop.log
```

## 2. Setup dotfiles
```sh
git clone git@github.com:jaronkk/dotfiles.git ~/.dotfiles
cd ~/.dotfiles
script/bootstrap
```

## 4. Apps

* [iTerm](https://www.iterm2.com/downloads.html)
* [Optimal Layout](https://itunes.apple.com/us/app/optimal-layout/id412627292?mt=12)
* [Adium](https://adium.im/)

### iTerm config
In Preferences -> General, under "Preferences" check the box "Load preferences from a custom folder or URL" and point it to `~/.dotfiles/iTerm`.

Restart iTerm for the changes to take effect.

### Adium config
```sh
cp ~/.dotfiles/Adium/Users/Default/* ~/Library/Application\ Support/Adium\ 2.0/Users/Default/
```

## 3. Brew packages

MySQL
```sh
brew install mysql
ln -sfv /usr/local/opt/mysql/*.plist ~/Library/LaunchAgents
launchctl load ~/Library/LaunchAgents/homebrew.mxcl.mysql.plist
```

RabbitMQ
```sh
brew install rabbitmq
ln -sfv /usr/local/opt/rabbitmq/*.plist ~/Library/LaunchAgents
launchctl load ~/Library/LaunchAgents/homebrew.mxcl.rabbitmq.plist
```

VIPS
```sh
brew tap homebrew/science
brew install vips
```
