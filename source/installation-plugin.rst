Installing the ckanext-dcatdonl plugin
===================================================================================================

Follow the steps listed below to install and activate the ckanext-dcatdonl extension into CKAN.

1. With your CKAN virtual environment activated:

.. code-block:: bash

    . /usr/lib/ckan/default/bin/activate
    pip install -e git+https://gitlab.textinfo.nl/opensource/ckanext-dcatdonl.git#egg=ckanext-dcatdonl
    cd ckanext-dcatdonl
    pip install -r requirements.txt

2. Edit your CKAN .ini configuration file and add the following

.. code-block:: ini

    ckan.plugins = ... dcatdonl

3. In the same file, add (or change) the following properties to:

.. code-block:: ini

    licenses_group_url = file:///usr/lib/ckan/default/src/ckanext-dcatdonl/ckanext/dcatdonl/resources/overheid_license.json
    solr_url = http://{{host}}:8983/solr/ckan
    ckan.mimetype_guess = None

4. Restart apache2

You have now successfully installed the `ckanext-dcatdonl` plugin
