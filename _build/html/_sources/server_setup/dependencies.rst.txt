Dependencies
=================================


Git
########
* Install `Git <https://git-scm.com/>`_

.. code-block:: console

    $ sudo apt-get install git

Check whether *git* has been installed correctly

.. code-block:: console

    $ git --version


Python
########
* Install `Python <https://www.python.org/>`_


v2.7
**********************

.. code-block:: console

    $ sudo apt-get install python-dev


* Install **setuptools** and **pip** (Python's Package Manager):

.. code-block:: console

    $ sudo apt-get install python-setuptools python-pip


v3.x
**********************

.. code-block:: console

    $ sudo apt-get install python3-dev


* Install **setuptools** and **pip** (Python's Package Manager):

.. code-block:: console

    $ apt-get install python3-setuptools python3-pip


* You can also create an alias for pip and python to enforce use of python 3:

.. code-block:: console

	alias python=python3
	alias pip=pip3


MariaDB
########
* Install `MariaDB <https://mariadb.org/>`_

To install MariaDB 10.3 stable package on your Linux OS, simply:


.. code-block:: console

	$ sudo apt-get install software-properties-common
	$ sudo apt-key adv --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 0xF1656F24C74CD1D8
	$ sudo add-apt-repository 'deb [arch=amd64,i386,ppc64el] http://ftp.ubuntu-tw.org/mirror/mariadb/repo/10.3/ubuntu xenial main'

	$ sudo apt-get update
	$ sudo apt-get install mariadb-server-10.3


During this installation you'll be prompted to set the MySQL root password. If you are not prompted for the same, you'll have to initialize the MySQL server setup yourself after the above command completes. You can initialize the MySQL server setup by executing the following command mysql_secure_installation. Remember: only run it if you're not prompted the password during setup.

It is really important that you remember this password, since it'll be needed later on! Test whether the installation has worked with mysql -u root -p -h localhost. You should be prompted for the mysql root password you have provided during the installation. Get back out of the mysql console by typing \q

Next you'll need the MySQL database development files


.. code-block:: console

	$ sudo apt-get install libmysqlclient-dev

You also need to edit the mariadb configuration (although the guide in README doesn't mention this, you'll face an error message asking you to do exactly this if you follow the README. So you might as well go ahead and do this)


.. code-block:: console

	$ sudo nano /etc/mysql/my.cnf

And add this to the file


.. code-block:: console

	[mysqld]
	character-set-client-handshake = FALSE
	character-set-server = utf8mb4
	collation-server = utf8mb4_unicode_ci

	[mysql]
	default-character-set = utf8mb4


(Now press (Ctrl-X) to exit!) Finally restart the mysql server and you'll be good to go!


.. code-block:: console

	$ sudo service mysql restart


Redis
########
* Install `Redis <https://redis.io/>`_


.. code-block:: console

	$ sudo apt-get install redis-server


Node.js 10.x and Yarn
########################

.. code-block:: console

	$ sudo apt-get install curl
	$ curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -
	$ sudo apt-get install -y nodejs

	$ sudo npm install -g yarn
