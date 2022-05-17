Dataset
=====================================================

.. list-table::
    :widths: 22 45 33
    :header-rows: 1

    * - Property
      - Description
      - Validation
    * - identifier
      - A global identifier that identifies the dataset
      - Required, String, Is URI
    * - alternate_identifier
      - Alternate identifiers that identify the dataset
      - Optional, List, Are URIs
    * - language
      - The languages used for the data found in the dataset
      - Required, From :code:`donl:language`
    * - authority
      - Entity that is responsible for the contents of the dataset
      - Required, String, From :code:`donl:organizations`
    * - publisher
      - Entity responsible for maintenance and publication of the dataset
      - Required, String, From :code:`donl:organizations`
    * - contact_point_email
      - Email of the contact point
      - Optional, String
    * - contact_point_address
      - Address of the contact point
      - Optional, String
    * - contact_point_name
      - Name of the contact point
      - Required, String
    * - contact_point_phone
      - Phonenumber of the contact point
      - Optional, String
    * - contact_point_website
      - Webaddress of the contact point
      - Optional, String
    * - contact_point_title
      - Title of the contact point, if it describes a person
      - Optional, String
    * - access_rights
      - The level of openness of the dataset
      - Optional, String, From :code:`overheid:openhaarheidsniveau`
    * - url
      - Webpage that provides additional information about the dataset, its metadata or its authority
      - Optional, String, Is URL
    * - conforms_to
      - Standards the dataset conforms to
      - Optional, List, Are URIs
    * - related_resource
      - Resources related to the dataset
      - Optional, List, Are URIs
    * - source
      - Dataset on which this dataset is based
      - Optional, List, Are URIs
    * - version
      - The version of the dataset
      - Optional, String
    * - version_notes
      - Version notes of the dataset
      - Optional, List, Strings
    * - issued
      - Date and time on which the dataset was published
      - Optional, String, :code:`yyyy-mm-ddThh:mm:ss`
    * - has_version
      - References to datasets which are based on this dataset
      - Optional, List
    * - is_version_of
      - References to datasets on which this dataset is based
      - Optional, List, Are URIs
    * - legal_foundation_ref
      - specific reference of the legal_foundation
      - Optional, String
    * - legal_foundation_uri
      - URI of the legal_foundation
      - Optional, String, Is URI
    * - legal_foundation_label
      - Label of the legal foundation
      - Optional, String
    * - frequency
      - How often the dataset is updated
      - Optional, String, From :code:`overheid:frequency`
    * - provenance
      - Webpages that describe how this dataset came to be
      - Optional, List, Are URLs
    * - documentation
      - Webpages about the dataset
      - Optional, List, Are URLs
    * - sample
      - Sample data of the dataset
      - Optional, List, Are URLs
    * - license_id
      - The license that applies to the dataset
      - Required, From :code:`overheid:license`
    * - title
      - The title of the dataset
      - Required, String
    * - notes
      - The description of the dataset
      - Required, String
    * - tags
      - Keywords to describe the dataset
      - Optional, List
    * - metadata_language
      - The language used in the metadata of the dataset
      - Required, List, From :code:`donl:language`
    * - theme
      - One or more themes that describe the dataset
      - Required, List, From :code:`overheid:taxonomiebeleidsagenda`
    * - source_catalog
      - The original catalog of the dataset
      - Optional, From :code:`donl:catalogs`
    * - changetype
      - The latest action taken on the dataset
      - From :code:`adms:changetype`, ckanext-dcatdonl will set the correct value for this property
    * - modified
      - The date and time this dataset was last modified
      - Required, String, :code:`yyyy-mm-ddThh:mm:ss`
    * - spatial_scheme
      - The schemes of the spatial value
      - Optional, List, From :code:`overheid:spatial_scheme`
    * - spatial_value
      - Geographical locations based on the spatial_schemes provided
      - Optional, List, Validates against schemes defined in spatial_scheme
    * - temporal_label
      - A name of a timeperiod
      - Optional, String
    * - temporal_start
      - A point in time, together with temporal_end it describes a period in time
      - Optional, String, :code:`yyyy-mm-ddThh:mm:ss` Must be smaller than temporal_end
    * - temporal_end
      - A point in time, together with temporal_start it describes a period in time
      - Optional, String, :code:`yyyy-mm-ddThh:mm:ss` Must be greater than temporal_start
    * - dataset_status
      - State of the dataset, it describes the availability of the dataset
      - Optional, String, From :code:`overheid:datasetStatus`, defaults to the URI for :code:`beschikbaar`
    * - date_planned
      - The date and time upon which it is planned that the dataset becomes available
      - Optional, String, :code:`yyyy-mm-ddThh:mm:ss`
    * - high_value
      - Indicates this dataset is considered of 'high value' by the Dutch government
      - Optional, Boolean, defaults to :code:`False`
    * - basis_register
      - Indicates this dataset is part of the Dutch 'basisregister'
      - Optional, Boolean, defaults to :code:`False`
    * - referentie_data
      - Indicates this dataset contains `highly` reusable data
      - Optional, Boolean, defaults to :code:`False`
    * - national_coverage
      - Indicates this dataset covers all of The Netherlands
      - Optional, Boolean, defaults to :code:`False`
