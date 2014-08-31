# Xdebug toggler for OSX

[Xdebug][xdebug] is a must have extension for php but the times you don't need it, it's a drag.

This simple script allows to toggle `on` and `off` [Xdebug][xdebug] and is meant for all the users who have `PHP` and `Xdebug` installed via [Homebrew][brew].

You can follow the _OS X Apache Setup_ guide, divided in two parts, to get the perfect MAMP setup on OSX:

* [Part 1: Multiple PHP Versions][tutorial-1]
* [Part 2: MySQL, APC & More...][tutorial-2]

>> This script is inspired by the great [sphp][sphp] script. Which I highly suggest to install if you need to switch easily between php versions

## Installation

```
git clone git@github.com:w00fz/xdebug-osx.git
```

Add `/usr/local/bin` to your `$PATH`. If you use the Bash shell, you can do this by running this command:
```
echo 'export PATH="/usr/local/bin:$PATH"' >> $HOME/.bashrc
```
You may need to restart your shell for this to take effect, or refrehs it with `source ~/.bashrc`.

## Usage
```
./xdebug-osx/xdebug on
./xdebug-osx/xdebug off
./xdebug-osx/xdebug status
```

## License
[LICENSE](LICENSE)

[xdebug]: http://xdebug.org/
[brew]: http://brew.sh/
[grav]: http://getgrav.org/
[tutorial-1]: http://getgrav.org/blog/mac-os-x-apache-setup-multiple-php-versions
[tutorial-2]: http://getgrav.org/blog/mac-os-x-apache-setup-mysql-vhost-apc
[sphp]: https://github.com/conradkleinespel/sphp-osx
