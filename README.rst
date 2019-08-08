Ansible Role for Authorization
==============================

|Build Status| |GitHub issues| |GitHub license|

:Version: 0.0.0
:Web: https://github.com/equipindustry/ansible-role-authorization
:Download: http://github.com/equipindustry/ansible-role-authorization
:Source: http://github.com/equipindustry/ansible-role-authorization
:Keywords: ansible-role-authorization

.. contents:: Table of Contents:
    :local:

Ansible Galaxy role for `Authorization`_.

Requirements:
-------------

List of applications:

- `Python 3.7.3`_
- `Docker`_
- `Docker Compose`_

Install
-------

Install it with the following command:

.. code-block:: bash

    $ ansible-galaxy install equipindustry.authorization

Role Variables
--------------

The default role variables in ``defaults/main.yml`` are:

.. code-block:: yaml

        authorization_key_dir: "/Volumes/Home/private/key_file/project"
        authorization:
        project:
            key_dir: "{{ authorization_key_dir }}"
            key_files:
            - key: id_rsa
                src: "{{ authorization_key_dir }}/id_rsa"
                path: "{{ app_dir_home }}/.ssh/id_rsa"
                permissions: 0600
                owner: "{{ user }}"
                state: file
            - key: id_rsa.pub
                src: "{{ authorization_key_dir }}/id_rsa.pub"
                path: "{{ app_dir_home }}/.ssh/id_rsa.pub"
                permissions: 0600
                state: file
                owner: "{{ user }}"

Dependencies
------------

None

Example Playbook
----------------

See the `examples <./examples/>`__ directory.

To run this playbook with default settings, create a basic playbook like
this:

.. code:: yaml

    - hosts: servers
        roles:
        - equipindustry.authorization

License
-------

Apache2

Changelog
---------

Please see `CHANGELOG`_ for more information what
has changed recently.

Contributing
------------

Please see `CONTRIBUTING`_ for details.

Credits
-------

-  `author`_
-  `contributors`_

Made with :heart: :coffee: and :pizza: by `author`_ and `company`_.

.. Badges:

.. |Build Status| image:: https://travis-ci.org/equipindustry/ansible-role-authorization.svg
   :target: https://travis-ci.org/equipindustry/ansible-role-authorization
.. |Ansible Galaxy| image:: https://img.shields.io/badge/galaxy-equipindustry.authorization-blue.svg
   :target: https://galaxy.ansible.com/equipindustry/ansible-role-authorization/
.. |GitHub issues| image:: https://img.shields.io/github/issues/equipindustry/ansible-role-authorization.svg
   :target: https://github.com/equipindustry/ansible-role-authorization/issues
.. |Average time to resolve an issue| image:: http://isitmaintained.com/badge/resolution/equipindustry/ansible-role-authorization.svg
   :target: http://isitmaintained.com/project/equipindustry/ansible-role-authorization
.. |Percentage of issues still open| image:: http://isitmaintained.com/badge/open/equipindustry/ansible-role-authorization.svg
   :target: http://isitmaintained.com/project/equipindustry/ansible-role-authorization
.. |GitHub license| image:: https://img.shields.io/github/license/mashape/apistatus.svg?style=flat-square
   :target: LICENSE

.. Link
.. _`changelog`: CHANGELOG.rst
.. _`contributors`: AUTHORS
.. _`contributing`: CONTRIBUTING.rst

.. _`company`: https://github.com/equipindustry
.. _`author`: https://github.com/luismayta

.. dependences
.. _Authorization: https://github.com/equipindustry/ansible-role-authorization
.. _Python: https://www.python.org
.. _Python 3.7.3: https://www.python.org/downloads/release/python-373
.. _Docker: https://www.docker.com/
.. _Docker Compose: https://docs.docker.com/compose/
