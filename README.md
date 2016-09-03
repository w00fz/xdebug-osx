# Xdebug Toggler for OSX

![](screenshot.png "Usage Example")

[Xdebug][xdebug] is a must have extension for PHP, although the times you don't actually need it, it's a drag.

This simple script allows to toggle `on` and `off` [Xdebug][xdebug] and is meant for anyone running `PHP` and `Xdebug` installed via [Homebrew][brew].

You can follow the _OS X Apache Setup_ guide, divided in two parts, to get the perfect MAMP setup on OSX:

* [Part 1: Multiple PHP Versions][tutorial-1]
* [Part 2: MySQL, APC & More...][tutorial-2]

>> This script is inspired by the great [sphp][sphp] script. Which I highly suggest to install if you need to switch easily between php versions

## Quick Installation

```
curl -L https://raw.githubusercontent.com/w00fz/xdebug-osx/master/xdebug-toggle > /usr/local/bin/xdebug-toggle
```

## Installation with homebrew

```
brew install xdebug-osx
```

## Installation with clone

```
git clone git@github.com:w00fz/xdebug-osx.git
```

Add `/usr/local/bin` to your `$PATH`. If you use the Bash shell, you can do this by running this command:
```
echo 'export PATH="/usr/local/bin:$PATH"' >> $HOME/.bashrc
```
You may need to restart your shell for this to take effect, or refrehs it with `source ~/.bashrc`.

If you want the global command then run:
```
cd xdebug-osx
ln -s `pwd`/xdebug-toggle /usr/local/bin/xdebug-toggle
```

## Make sure `xdebug-toggle` is executable

```
chmod +x /usr/local/bin/xdebug-toggle
```

## Usage
```
xdebug-toggle                            # outputs the current status
xdebug-toggle on                         # enables xdebug
xdebug-toggle off                        # disables xdebug
xdebug-toggle on|off --no-server-restart # toggles xdebug without restarting apache or php-fpm
```

## License
[LICENSE](LICENSE)

[xdebug]: http://xdebug.org/
[brew]: http://brew.sh/
[grav]: http://getgrav.org/
[tutorial-1]: http://getgrav.org/blog/mac-os-x-apache-setup-multiple-php-versions
[tutorial-2]: http://getgrav.org/blog/mac-os-x-apache-setup-mysql-vhost-apc
[sphp]: https://github.com/conradkleinespel/sphp-osx
