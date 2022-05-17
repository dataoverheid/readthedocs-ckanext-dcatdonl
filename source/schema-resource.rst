Resource
=====================================================

.. list-table::
    :widths: 22 45 33
    :header-rows: 1

    * - Property
      - Description
      - Validation
    * - url
      - The URL used to access the resource
      - Required, String, Is URI
    * - name
      - The name of the resource
      - Required, String
    * - description
      - A description of the resource
      - Required, String
    * - metadata_language
      - The language used in the metadata of the resource
      - Required, String, From :code:`donl:language`
    * - language
      - The languages used for the data found in the resource
      - Required, List, From :code:`donl:language`
    * - license_id
      - The license that applies to the resource
      - Required, From :code:`overheid:license`
    * - format
      - The format of the resource
      - Required, String, From :code:`mdr:filetype_nal`
    * - size
      - The size of the contents of the resource in kilobytes
      - Optional, Positive integer
    * - download_url
      - List of URLs referring to downloadable variants of the resource
      - Optional, List, Are URLs
    * - mimetype
      - Mimetype of the resource
      - Optional, String, From :code:`iana:mediatypes`
    * - release_date
      - The date the resource was released
      - Optional, String, :code:`yyyy-mm-ddThh:mm:ss`
    * - rights
      - Rights that apply to the resource
      - Optional, String
    * - status
      - Distributionstatus of the resource
      - Optional, String, From :code:`adms:distributiestatus`
    * - modification_date
      - Date on which this resource was last modified
      - Optional, String, :code:`yyyy-mm-ddThh:mm:ss`
    * - linked_schemas
      - Standards the resource applies to
      - Optional, List, Are URIs
    * - hash
      - A hash calculated based on the contents of the resource
      - Optional, String
    * - hash_algorithm
      - The hash algorithm used to determine the hash
      - Optional, String
    * - documentation
      - A list of URLs that refer to documentation of the resource
      - Optional, List, Are URLs
