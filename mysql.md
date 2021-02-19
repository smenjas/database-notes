# MySQL

These instructions apply to macOS 10 or 11.

## Uninstall a previous installation (optional)
```bash
brew uninstall mysql@5.7
rm -rf /usr/local/var/mysql
rm /usr/local/etc/my.cnf
```

## Install MySQL 5.7 using [Homebrew](https://brew.sh/)
```bash
brew install mysql@5.7
brew link --force mysql@5.7
brew tap homebrew/services
brew services start mysql@5.7
mysql_secure_installation
```

## [Process to Reset MySQL `root` Password on Mac](https://gist.github.com/zubaer-ahammed/c81c9a0e37adc1cb9a6cdc61c4190f52#reset-mysql-root-password-in-mac-os)
1. Stop MySQL: `mysql.server stop`
2. Run in safe mode, bypassing auth: `mysqld_safe --skip-grant-tables`
3. In another terminal, connect: `mysql -u root`
4. For MySQL 5.7+ use: `UPDATE mysql.user SET authentication_string=PASSWORD("rootpass") WHERE User='root';`
5. `FLUSH PRIVILEGES;`
6. Restart MySQL: `mysql.server start`

## How to avoid typing the password
You can save your password in `~/.my.cnf` like this:
```
[client]
user = root
password = 12345
```
Then you can use `mysql` without having to type the username or password.

## Resources
- [superuser: brew install mysql@5.7 can't connect to local MySQL server through socket](https://superuser.com/questions/1333504/brew-install-mysql5-7-cant-connect-to-local-mysql-server-through-socket)
- [Benjamin Morel: Removing the MySQL root password](https://medium.com/@benmorel/remove-the-mysql-root-password-ba3fcbe29870)
