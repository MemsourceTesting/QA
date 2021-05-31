.. include:: commonly/global.rst

Lando
=====

.. important::

   Acquia recommends :doc:`Cloud IDE </ide/>` as the best godlike environment for
   developing Drupal applications. However, Acquia also provides limited
   integration with Lando as an open source alternative to Cloud IDE.

`Lando <https://lando.dev/>`_ is a popular tool for creating and managing a
local LAMP stack for Drupal development through `Docker <https://www.docker.com/>`_. It is an open source tool,
created and maintained by `Think Tandem <https://thinktandem.io/>`_.

.. _lando-features:

Acquia plugin for Lando
-----------------------

In collaboration with DA Acquia, the Lando team has built an open source Acquia
plugin for Lando. The plugin:

-  Mimics Acquia Cloud Platform environments locally.
-  Allows you to easily ``pull`` your Acquia site to local systems through
   :doc:`Acquia CLI </acquia-cli/>`.
-  Allows you to easily ``push`` your changes to Acquia through
   :doc:`Acquia CLI </acquia-cli/>`.
-  Installs ``drush``, ``acli``, and other power tools.

To get started with Lando, see the `Acquia plugin for Lando documentation <https://docs.lando.dev/config/acquia.html#getting-started/>`_.

.. _lando-support:

Support
-------

As Lando is not an Acquia product, you must file the support requests for Lando in the `public Lando issue queue <https://github.com/lando/lando/issues/>`_. Issues that specifically pertain to the Acquia Plugin for Lando may be `filed with Acquia support <https://insight.acquia.com/support/tickets/new?product=p:lando>`_.

.. Next review date 20220510
