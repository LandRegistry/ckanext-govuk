.. You should enable this project on travis-ci.org and coveralls.io to make
   these badges work. The necessary Travis and Coverage config files have been
   generated for you.

.. image:: https://coveralls.io/repos//ckanext-govuk/badge.svg
  :target: https://coveralls.io/r//ckanext-govuk

.. image:: https://pypip.in/download/ckanext-govuk/badge.svg
    :target: https://pypi.python.org/pypi//ckanext-govuk/
    :alt: Downloads

.. image:: https://pypip.in/version/ckanext-govuk/badge.svg
    :target: https://pypi.python.org/pypi/ckanext-govuk/
    :alt: Latest Version

.. image:: https://pypip.in/py_versions/ckanext-govuk/badge.svg
    :target: https://pypi.python.org/pypi/ckanext-govuk/
    :alt: Supported Python versions

.. image:: https://pypip.in/status/ckanext-govuk/badge.svg
    :target: https://pypi.python.org/pypi/ckanext-govuk/
    :alt: Development Status

.. image:: https://pypip.in/license/ckanext-govuk/badge.svg
    :target: https://pypi.python.org/pypi/ckanext-govuk/
    :alt: License

=============
ckanext-govuk
=============

This extension includes the assets, styles and javascript functionality of govuk-frontend 
to enable data publication services to be implemented using ckan for hosting on GOV.UK


------------
Requirements
------------

`ckan 2.8.2 <https://github.com/ckan/ckan/releases/tag/ckan-2.8.2>`_


------------
Installation
------------

.. Add any additional install steps to the list below.
   For example installing any non-Python dependencies or adding any required
   config settings.

To install ckanext-govuk:

1. Activate your CKAN virtual environment, for example::

     . /usr/lib/ckan/default/bin/activate

2. Install the ckanext-govuk Python package into your virtual environment::

     pip install ckanext-govuk (not currently available via pip)

3. Add ``govuk`` to the ``ckan.plugins`` setting in your CKAN
   config file (by default the config file is located at
   ``/etc/ckan/default/production.ini``).

4. Restart CKAN. For example if you've deployed CKAN with Apache on Ubuntu::

     sudo service apache2 reload


---------------
Config Settings
---------------

Document any optional config settings here. For example::

    # The minimum number of hours to wait before re-checking a resource
    # (optional, default: 24).
    ckanext.govuk.some_setting = some_default_value


------------------------
Development Installation
------------------------

To install ckanext-govuk for development, activate your CKAN virtualenv and
do::

    git clone https://github.com/LandRegistry/ckanext-govuk.git
    cd ckanext-govuk
    python setup.py develop
    pip install -r dev-requirements.txt


-----------------
Running the Tests
-----------------

To run the tests, do::

    nosetests --nologcapture --with-pylons=test.ini

To run the tests and produce a coverage report, first make sure you have
coverage installed in your virtualenv (``pip install coverage``) then run::

    nosetests --nologcapture --with-pylons=test.ini --with-coverage --cover-package=ckanext.govuk --cover-inclusive --cover-erase --cover-tests


---------------------------------
Registering ckanext-govuk on PyPI
---------------------------------

ckanext-govuk should be availabe on PyPI as
https://pypi.python.org/pypi/ckanext-govuk. If that link doesn't work, then
you can register the project on PyPI for the first time by following these
steps:

1. Create a source distribution of the project::

     python setup.py sdist

2. Register the project::

     python setup.py register

3. Upload the source distribution to PyPI::

     python setup.py sdist upload

4. Tag the first release of the project on GitHub with the version number from
   the ``setup.py`` file. For example if the version number in ``setup.py`` is
   0.0.1 then do::

       git tag 0.0.1
       git push --tags


----------------------------------------
Releasing a New Version of ckanext-govuk
----------------------------------------

ckanext-govuk is availabe on PyPI as https://pypi.python.org/pypi/ckanext-govuk.
To publish a new version to PyPI follow these steps:

1. Update the version number in the ``setup.py`` file.
   See `PEP 440 <http://legacy.python.org/dev/peps/pep-0440/#public-version-identifiers>`_
   for how to choose version numbers.

2. Create a source distribution of the new version::

     python setup.py sdist

3. Upload the source distribution to PyPI::

     python setup.py sdist upload

4. Tag the new release of the project on GitHub with the version number from
   the ``setup.py`` file. For example if the version number in ``setup.py`` is
   0.0.2 then do::

       git tag 0.0.2
       git push --tags


------------------------------------------------
Updating to the Latest Version of govuk-frontend
------------------------------------------------

Currently this ckan extension uses the minified versions of the govuk assets to implement all of 
the govuk styles and functionality. In order to update to the latest version of the govuk frontend 
then you will need to follow the manual steps below:

1. Download the latest version of the `govuk-frontend assets <https://github.com/alphagov/govuk-frontend/tree/master/dist>`_.
2. Put all of the downloaded fonts and images into the appriopriate folder in ``ckanext/public/assets``, replacing the files already in there.
3. Put all of the minified css and javascript files into the folder ``ckanext/public``, replacing the files already in there.
4. Update all of the links for the css and javascript in ``ckanext/templates/base.html`` to point to the latest versions.


------------
Useful links
------------

**CKAN**

- `ckan 2.8.2 documentation <https://docs.ckan.org/en/2.8/>`_
- `ckan 2.8.2 api guide <https://docs.ckan.org/en/2.8/api/>`_
- `ckan 2.8.2 plugin interfaces <https://docs.ckan.org/en/2.8/extensions/plugin-interfaces.html>`_

**GOV.UK Frontend**

- `govuk-frontend <https://github.com/alphagov/govuk-frontend>`_
