# Xdebug Toggler for OSX

![](screenshot.png "Usage Example")

[Xdebug][xdebug] is a must have extension for PHP, although the times you don't actually need it, it's a drag.

This simple script allows to toggle `on` and `off` [Xdebug][xdebug] and is meant for anyone running `PHP` and `Xdebug` installed via [Homebrew][brew].

You can follow the _OS X Apache Setup_ guide, divided in two parts, to get the perfect MAMP setup on OSX:

* [Part 1: Multiple PHP Versions][tutorial-1]
* [Part 2: MySQL, APC & More...][tutorial-2]

>> This script is inspired by the great [sphp][sphp] script. Which I highly suggest to install if you need to switch easily between php versions.
>> However since it's been quite inactive I am now running and maintaning my own implementation. You can get it from https://gist.github.com/w00fz/142b6b19750ea6979137b963df959d11

## Quick Installation

```
curl -L https://raw.githubusercontent.com/w00fz/xdebug-osx/master/xdebug-toggle > /usr/local/bin/xdebug-toggle
```

## Installation with clone

```
git clone git@github.com:w00fz/xdebug-osx.git
```

Add `/usr/local/bin` to your `$PATH`. If you use the Bash shell, you can do this by running this command:
```
echo 'export PATH="/usr/local/bin:$PATH"' >> $HOME/.bashrc
```
You may need to restart your shell for this to take effect, or refresh it with `source ~/.bashrc`.

If you want the global command then run:
```
cd xdebug-osx
ln -s `pwd`/xdebug-toggle /usr/local/bin/xdebug-toggle
```

## Make sure `xdebug-toggle` is executable

```
chmod +x /usr/local/bin/xdebug-toggle
```

## Xdebug installation and configuration

Homebrew does not provide a keg for Xdebug anymore, so you must install Xdebug extension via pecl

```bash
pecl channel-update pecl.php.net
pecl install xdebug
```

`xdebug-toggle` needs a file called `ext-xdebug.ini` in brew's php conf.d directory to work, which must contain, at least, the following:

```ini
zend_extension="xdebug.so"
```

Make sure that `php.ini` doesn't contain this line too.

It's recommended to keep al xdebug config in this file, as an example:

```ini
[xdebug]
zend_extension="xdebug.so"

xdebug.var_display_max_depth=24
xdebug.remote_port=9000
xdebug.remote_enable=1
xdebug.remote_connect_back=1
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
