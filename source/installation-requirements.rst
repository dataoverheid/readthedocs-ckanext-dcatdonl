Requirements
===========================================

The plugin was developed with the following versions in mind.

CKAN
-------------------------------------------
The plugin functions correctly with these CKAN versions:

.. list-table::
    :widths: 25 75
    :header-rows: 1

    * - Version
      - Reference
    * - `2.7.3`
      - http://docs.ckan.org/en/ckan-2.7.3/
    * - `2.7.4`
      - http://docs.ckan.org/en/2.7/
    * - `2.8.0`
      - http://docs.ckan.org/en/2.8/

It is likely that the plugin functions correctly in earlier and later versions, however only the
above mentioned CKAN versions have been tested and confirmed to work.

PostgreSQL
-------------------------------------------

CKAN uses PostgreSQL with version :code:`9.2` or higher.

Python
-------------------------------------------

CKAN itself, and the ckanext-dcatdonl plugin are written in :code:`Python 2.7.x`. As such, the
CKAN host must have this version of Python installed.
