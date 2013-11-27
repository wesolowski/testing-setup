# Workshop Testing Setup

Please make sure that you have a working setup of:

* PHP 5.3 (or newer)
* A Git client

## Installation

1. Make sure PHP is installed on your machine. The following link has more information on how to install PHP:
   http://www.phptherightway.com/#getting\_started
   On a Debian/Ubuntu-based machine installing PHP is as simple as calling `apt-get install php5 php5-cli` as root user.
2. Make sure [Composer](http://getcomposer.org/) is installed on your machine.
   Composer is a dependency management tool. It will will download the code as
   zip packages from Github Download servers. For installation instructions
   see: http://getcomposer.org/download/
3. Using your Git client, checkout https://github.com/QafooLabs/testing-setup.git to a directory of your
   choice. On the shell you can do that using `$ git clone https://github.com/QafooLabs/testing-setup.git`.
4. Switch into the directory of the checkout and call `$ php composer.phar install --dev --prefer-dist`
   to install all the dependencies.
5. Try to execute PHPUnit using `$ vendor/bin/phpunit`, the result should be a single successful test run.

## Links

* http://www.phpunit.de/manual/current/en/installation.html
* http://git-scm.com/downloads

## Vagrant setup (optional)

For those who are interested there is a vagrant setup available (optional).
Just follow these steps to get up and running with your own Virtual environment.

* Install [Virtualbox](https://www.virtualbox.org/) and [Vagrant](http://www.vagrantup.com)
* From the root of this git repository run `vagrant up` and wait for the VM to boot and provision
* Ssh into the VM by running `vagrant ssh` and switch to the `/vagrant` directory

Once in the virtual machine you can find all files in `/vagrant`, this is actually the folder on your machine (the host) you ran the `vagrant up` command from, mounted into the Virtual machine. All changes made to files inside this directory on your computer will reflect immediately on the Virtual machine. This makes that you can run PHPUnit on the VM through an ssh session while still being able to edit the files on your computer with your favourite editor or IDE.

To test if all is installed correct run `phpunit test/` from the `/vagrant` folder in your VM.
