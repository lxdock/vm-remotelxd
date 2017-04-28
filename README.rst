vm-remotelxd
############

This Vagrantfile will create a machine containing an installation of LXD with a pre-configred remote
LXD server.

Usage
=====

Create the remote LXD server with:

.. code-block:: console

  $ vagrant up

In order to use the remote LXD server with your local LXD client, you have to make sure that your
local LXD is visible to the network so you can transfer containers and images from it:

.. code-block:: console

  $ lxc config set core.https_address [::]:8443

Finally you can add the remote LXD server to your local LXD by running:

.. code-block:: console

  $ lxc remote add remotetest 172.48.127.10

License
=======

GPLv3. See ``LICENSE`` for more details.
