Installation of Solr
===================================================================================================

To install Solr version 7.5.0 (assuming no previous Solr installation):

.. code-block:: bash

    sudo apt-get install openjdk-9-jre-headless
    cd /opt
    sudo wget http://www-eu.apache.org/dist/lucene/solr/7.5.0/solr-7.5.0.tgz
    sudo tar xzf solr-7.5.0.tgz solr-7.5.0/bin/install_solr_service.sh --strip-components=2
    sudo bash ./install_solr_service.sh solr-7.5.0.tgz

To create the CKAN core into Solr:

.. code-block:: bash

    sudo -u solr /opt/solr/bin/solr create -c ckan
    sudo rm /var/solr/data/ckan/conf/protwords.txt
    sudo rm /var/solr/data/ckan/conf/solrconfig.xml
    sudo rm /var/solr/data/ckan/conf/managed-schema
    sudo rm /var/solr/data/ckan/conf/stopwords.txt
    sudo rm /var/solr/data/ckan/conf/synonyms.txt
    sudo mkdir /var/lib/solr
    sudo chown solr /var/lib/solr -R
    cd ~
    sudo ln -s /usr/lib/ckan/default/src/ckanext-dcatdonl/ckanext/dcatdonl/resources/solr/7.4/currency.xml /var/solr/data/ckan/conf
    sudo ln -s /usr/lib/ckan/default/src/ckanext-dcatdonl/ckanext/dcatdonl/resources/solr/7.4/elevate.xml /var/solr/data/ckan/conf
    sudo ln -s /usr/lib/ckan/default/src/ckanext-dcatdonl/ckanext/dcatdonl/resources/solr/7.4/protwords.txt /var/solr/data/ckan/conf
    sudo ln -s /usr/lib/ckan/default/src/ckanext-dcatdonl/ckanext/dcatdonl/resources/solr/7.4/schema.xml /var/solr/data/ckan/conf
    sudo ln -s /usr/lib/ckan/default/src/ckanext-dcatdonl/ckanext/dcatdonl/resources/solr/7.4/solrconfig.xml /var/solr/data/ckan/conf
    sudo ln -s /usr/lib/ckan/default/src/ckanext-dcatdonl/ckanext/dcatdonl/resources/solr/7.4/spellings.txt /var/solr/data/ckan/conf
    sudo ln -s /usr/lib/ckan/default/src/ckanext-dcatdonl/ckanext/dcatdonl/resources/solr/7.4/stopwords.txt /var/solr/data/ckan/conf
    sudo ln -s /usr/lib/ckan/default/src/ckanext-dcatdonl/ckanext/dcatdonl/resources/solr/7.4/synonyms.txt /var/solr/data/ckan/conf
    sudo ln -s /usr/lib/ckan/default/src/ckanext-dcatdonl/ckanext/dcatdonl/resources/solr/7.4/synonyms_themes.txt /var/solr/data/ckan/conf
    sudo ln -s /usr/lib/ckan/default/src/ckanext-dcatdonl/ckanext/dcatdonl/resources/solr/7.4/synonyms_themes_hierarchy.txt /var/solr/data/ckan/conf
    sudo service solr restart

If your want to use the ckanext-dcatdonl solr optimizations for earlier CKAN versions it is advised to use the files present in the `ckanext/dcatdonl/resources/solr/5.5` directory instead.