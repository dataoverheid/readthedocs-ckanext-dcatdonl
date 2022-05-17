Changes applied on 29/10/2018
============================================

A new version has been released, the changes are list below!

- updated installation instructions.
    - Now includes the installation of additional requirements
    - Added instructions for targeting specific Apache Solr versions
- Introduced instructions to setup Apache Solr in various versions
    - Currently contains support for Apache Solr 5.4 and 7.4
- Introduced several backwards compatible fixes for CKAN versions below 2.6
- Included Solr optimizations, searches against Solr now include several facets by default, namely
    - facet_referentie_data
    - facet_access_rights
    - facet_publisher
    - facet_authority
    - facet_high_value
    - facet_basis_register
    - facet_dataset_status
    - facet_metadata_language
    - facet_frequency
    - facet_license_id
    - facet_source_catalog
    - facet_theme
- Changes to the schemas:
    - To declare a license for a package and/or resource you must now provide it in the :code:`license_id` key rather than the `license` key.
    - The fields :code:`highvalue`, :code:`basisregister` and :code:`referentiedata` are no longer considered data.overheid system properties and are now part of the base DCAT-AP-DONL scheme
    - The field :code:`highvalue` has been renamed to :code:`high_value`
    - The field :code:`referentiedata` has been renamed to :code:`referentie_data`
    - The field :code:`basisregister` has been renamed to :code:`basis_register`
    - The field :code:`dataset_status` will now default to the URI for :code:`beschikbaar`
    - The field :code:`high_value` will now default to :code:`false`
    - The field :code:`referentie_data` will now default to :code:`false`
    - The field :code:`basis_register` will now default to :code:`false`
    - The list validation is now less strict, when a single value is provided it will silently convert this to a list of size 1 rather than returning a validation error message
- Updated the Usage chapter to incorporate the changes to the schemas
- The documented error messages have been updated
- Updated the logging format of the :code:`controlled_vocabulary_updater.py`
- Small fixes to various chapters of this documentation containing inaccuracies
