# Brave browser
	sudo apt install curl
	sudo curl -fsSLo /usr/share/keyrings/brave-browser-archive-keyring.gpg https://brave-browser-apt-release.s3.brave.com/brave-browser-archive-keyring.gpg
	echo "deb [signed-by=/usr/share/keyrings/brave-browser-archive-keyring.gpg] https://brave-browser-apt-release.s3.brave.com/ stable main"|sudo tee /etc/apt/sources.list.d/brave-browser-release.list
	sudo apt update
	sudo apt install brave-browser
	
# Git
	(git is sometimes already installed by default - if not) -> sudo apt-get install git

# XAMPP
	gives permission to xampp installer: sudo chmod +x xampp-linux-x64-8.2.0-0-installer.run
	run the installer: sudo ./xampp-linux-x64-8.2.0-0-installer.run
	install netstat: sudo apt-get install net-tools
	launch XAMPP: sudo /opt/lampp/lampp start
	stop XAMPP: sudo /opt/lampp/stop
	
# VS Code editor
	Snap works fine

# WordPress
	download latest WordPress from the official wordpress.org website

# Kdenlive
	download image from the official kdenlive website

# App Image Launcher
	sudo add-apt-repository ppa:appimagelauncher-team/stable
	sudo apt-get update
	sudo apt-get install appimagelauncher
	
# Nodejs
	Method 1:
	(from nodejs.org) -> download: .tar archive
	(go to the folder location) -> extract it with: tar -xf node-v18.15.0-linux-x64.tar.xz
	(move the extract folder to /home) -> edit .bashrc file: nano .bashrc
	(go to last line of file) -> write: export PATH=$PATH:/home/kev/node-v18.15.0-linux-x64/bin
	(save file) -> Ctrl+S
	(exite nano) -> Ctrl+X
	
	Method 2:
	install old version of node: sudo apt install nodejs
	install npm: sudo apt install npm
	install n: sudo npm install -g n
	upgrade to lts: sudo n lts
	(update npm) -> npm update -g
	npm install vite
	
# PHP
	sudo apt install --no-install-recommends php8.2
		(The --no-install-recommends flag will ensure that other packages like the Apache web server are not installed.)
	sudo apt-get install php8.2-xml
	install mysql driver: sudo apt-get install php-mysql
	enable extension in the php.ini file: extension=pdo_mysql.so OR extension=pdo_mysql
	check if everything correct: php -m
	check PDO: php -i |grep PDO
	(in case of problems with above do this) -> sudo apt-get --purge remove php-common
	(and after) -> sudo apt-get install php-common php-mysql php-cli
	
# Laravel
	(We need nodejs first: see above)
	from getcomposer.org:
		php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
		php -r "if (hash_file('sha384', 'composer-setup.php') === '55ce33d7678c5a611085589f1f3ddf8b3c52d662cd01d4ba75c0ee0459970c2200a51f492d557530c71c15d8dba01eae') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
		php composer-setup.php
		php -r "unlink('composer-setup.php');"
	move composer.phar to a directory that is in our path: sudo mv composer.phar /usr/local/bin/composer
	install laravel via composer: composer global require laravel/installer
	check paths: echo $PATH
	(if needed manually add composer to global path) ->  echo 'export PATH="$HOME/.config/composer/vendor/bin:$PATH"'
	 echo 'export PATH="$HOME/.config/composer/vendor/bin:$PATH"' >> ~/.bashrc
	 source ~/.bashrc
	 check again the path: echo $PATH (composer has to appear somewhere as a result)
	 (from the root of lavaral app): composer update

# Remove packages
	apt-get remove packagename
	apt-get remove --purge packagename
	apt-get autoremove
	sudo apt remove package_name
	sudo apt autoremove
	sudo apt purge package_name
	example: sudo apt purge php8.1*
