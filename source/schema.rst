CKAN Schema
====================================================

The ckanext-dcatdonl extension extends the CKAN schema for datasets and resources in such a way
that they are capable of holding metadata according to the DCAT-AP-DONL 1.1 metadata standard.

Not all the names of the properties used in this plugin match the vocabulary used in the
DCAT-AP-DONL 1.1 metadata standard specification. Instead, the plugin tries to follow the mapping
outlined in `github.com/ckan/ckanext-dcat#rdf-dcat-to-ckan-dataset-mapping`_.

.. toctree::
   :maxdepth: 2
   :caption: Contents

   schema-dcatmapping
   schema-dataset
   schema-resource
   schema-validation
   schema-valuelists

.. _github.com/ckan/ckanext-dcat#rdf-dcat-to-ckan-dataset-mapping: https://github.com/ckan/ckanext-dcat#rdf-dcat-to-ckan-dataset-mapping
