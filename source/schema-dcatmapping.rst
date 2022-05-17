DCAT to CKAN mapping
===================================================

In the tables below the exact mapping of DCAT-AP-DONL properties to their CKAN schema counterparts
is shown.

DCAT Dataset
---------------------------------------------------

.. list-table::
    :widths: 50 50
    :header-rows: 1

    * - DCAT Property
      - CKAN Property
    * - Dataset.identifier
      - Dataset.identifier
    * - Dataset.description
      - Dataset.notes
    * - Dataset.title
      - Dataset.name
    * - Dataset.language
      - Dataset.language
    * - Dataset.license
      - Dataset.license_id
    * - Dataset.modified
      - Dataset.modified
    * - Dataset.contactPoint
      - Dataset.contact_point_name
    * -
      - Dataset.contact_point_email
    * -
      - Dataset.contact_point_website
    * -
      - Dataset.contact_point_phone
    * -
      - Dataset.contact_point_address
    * -
      - Dataset.contact_point_title
    * - Dataset.distribution
      - Dataset.resources
    * - Dataset.keyword
      - Dataset.tags
    * - Dataset.publisher
      - Dataset.publisher
    * - Dataset.theme
      - Dataset.theme
    * - Dataset.landingPage
      - Dataset.url
    * - Dataset.spatial
      - Dataset.spatial_scheme
    * -
      - Dataset.spatial_value
    * - Dataset.temporal
      - Dataset.temporal_label
    * -
      - Dataset.temporal_start
    * -
      - Dataset.temporal_end
    * - Dataset.authority
      - Dataset.authority
    * - Dataset.accessRights
      - Dataset.access_rights
    * - Dataset.conformsTo
      - Dataset.conforms_to
    * - Dataset.documentation
      - Dataset.documentation
    * - Dataset.frequency
      - Dataset.frequency
    * - Dataset.hasVersion
      - Dataset.has_version
    * - Dataset.isVersionOf
      - Dataset.is_version_of
    * - Dataset.otherIdentifier
      - Dataset.alternative_identifier
    * - Dataset.provenance
      - Dataset.provenance
    * - Dataset.relatedResource
      - Dataset.related_resource
    * - Dataset.releaseDate
      - Dataset.issued
    * - Dataset.sample
      - Dataset.sample
    * - Dataset.source
      - Dataset.source
    * - Dataset.version
      - Dataset.version
    * - Dataset.versionNotes
      - Dataset.version_notes
    * - Dataset.grondslag
      - Dataset.legal_foundation_ref
    * -
      - Dataset.legal_foundation_uri
    * -
      - Dataset.legal_foundation_label
    * - Dataset.datasetStatus
      - Dataset.dataset_status
    * - Dataset.datePlanned
      - Dataset.date_planned
    * - Dataset.highValue
      - Dataset.high_value
    * - Dataset.basisregister
      - Dataset.basis_register
    * - Dataset.referentieData
      - Dataset.referentie_data
    * - Dataset.nationalCoverage
      - Dataset.national_coverage

DCAT Distribution
---------------------------------------------------

.. list-table::
    :widths: 50 50
    :header-rows: 1

    * - DCAT Property
      - CKAN Property
    * - Distribution.accessURL
      - Resource.url
    * - Distribution.description
      - Resource.description
    * - Distribution.format
      - Resource.format
    * - Distribution.license
      - Resource.license_id
    * - Distribution.byteSize
      - Resource.size
    * - Distribution.checksum
      - Resource.hash
    * -
      - Resource.hash_algorithm
    * - Distribution.documentation
      - Resource.documentation
    * - Distribution.downloadURL
      - Resource.download_url
    * - Distribution.language
      - Resource.language
    * - Distribution.linkedSchemas
      - Resource.linked_schemas
    * - Distribution.mediaType
      - Resource.mimetype
    * - Distribution.releaseDate
      - Resource.release_date
    * - Distribution.rights
      - Resource.rights
    * - Distribution.status
      - Resource.status
    * - Distribution.title
      - Resource.name
    * - Distribution.modified
      - Resource.modification_date

DCAT CatalogRecord
---------------------------------------------------

.. list-table::
    :widths: 50 50
    :header-rows: 1

    * - DCAT Property
      - CKAN Property
    * - CatalogRecord.modified
      - Dataset.metadata_modified
    * - CatalogRecord.conformsTo
      - Dataset.conforms_to
    * - CatalogRecord.changeType
      - Dataset.changetype
    * - CatalogRecord.listingDate
      - Dataset.metadata_created
    * - CatalogRecord.description
      - Dataset.notes
    * - CatalogRecord.language
      - Dataset.metadata_language
    * - CatalogRecord.sourceMetadata
      - Dataset.source_catalog
    * - CatalogRecord.title
      - Dataset.title
