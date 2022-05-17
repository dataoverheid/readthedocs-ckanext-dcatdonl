Valuelists
=====================================================

The following valuelists (AKA controlled vocabularies) are used to validate parts of the CKAN schemas.

.. list-table::
    :widths: 32 68
    :header-rows: 1

    * - Name
      - Location
    * - adms:changetype
      - https://waardelijsten.dcat-ap-donl.nl/adms_changetype.json
    * - adms:distributiestatus
      - https://waardelijsten.dcat-ap-donl.nl/adms_distributiestatus.json
    * - donl:catalogs
      - https://waardelijsten.dcat-ap-donl.nl/donl_catalogs.json
    * - donl:language
      - https://waardelijsten.dcat-ap-donl.nl/donl_language.json
    * - donl:organization
      - https://waardelijsten.dcat-ap-donl.nl/donl_organization.json
    * - iana:mediatypes
      - https://waardelijsten.dcat-ap-donl.nl/iana_mediatypes.json
    * - mdr:filetype_nal
      - https://waardelijsten.dcat-ap-donl.nl/mdr_filetype_nal.json
    * - overheid:datasetStatus
      - https://waardelijsten.dcat-ap-donl.nl/overheid_dataset_status.json
    * - overheid:frequency
      - https://waardelijsten.dcat-ap-donl.nl/overheid_frequency.json
    * - overheid:license
      - https://waardelijsten.dcat-ap-donl.nl/overheid_license.json
    * - overheid:openbaarheidsniveau
      - https://waardelijsten.dcat-ap-donl.nl/overheid_openbaarheidsniveau.json
    * - overheid:spatial_gemeente
      - https://waardelijsten.dcat-ap-donl.nl/overheid_spatial_gemeente.json
    * - overheid:spatial_koninkrijksdeel
      - https://waardelijsten.dcat-ap-donl.nl/overheid_spatial_koninkrijksdeel.json
    * - overheid:spatial_provincie
      - https://waardelijsten.dcat-ap-donl.nl/overheid_spatial_provincie.json
    * - overheid:spatial_scheme
      - https://waardelijsten.dcat-ap-donl.nl/overheid_spatial_scheme.json
    * - overheid:spatial_waterschap
      - https://waardelijsten.dcat-ap-donl.nl/overheid_spatial_waterschap.json
    * - overheid:taxonomiebeleidsagenda
      - https://waardelijsten.dcat-ap-donl.nl/overheid_taxonomiebeleidsagenda.json

Structure
-----------------------------------------------------

All valuelists are served as :code:`application/json`. The contents of these valuelist follows the
pattern outlined below, which shows a sample of the :code:`overheid:taxonomiebeleidsagenda`
valuelist:

.. code-block:: json

    {
        "http://standaarden.overheid.nl/owms/terms/Afval_(thema)": {
            "labels":   {
                            "nl-NL":    "Afval",
                            "en-US":    "Rubbish"
                        }
        },
        "http://standaarden.overheid.nl/owms/terms/Arbeidsomstandigheden_(thema)": {
            "labels":   {
                            "nl-NL":    "Arbeidsomstandigheden",
                            "en-US":    "Labour conditions"
                        }
        },
        ...
    }

When supplying a value that must be part of a valuelist, provide the key of the value. In the
example above this would be
:code:`http://standaarden.overheid.nl/owms/terms/Arbeidsomstandigheden_(thema)`. The labels are
provided so that front-end applications can provide a proper translation of the value.

The one exception to the format displayed above is for the valuelist of :code:`overheid:license`.
The format deviates here to accommodate CKAN, since CKAN requires its license source file to fit a
specific format. This format is displayed below.

.. code-block:: json

    [
        {
            "domain_content":   false,
            "domain_data":      false,
            "domain_software":  false,
            "family":           "",
            "id":               "notspecified",
            "is_generic":       true,
            "maintainer":       "",
            "od_conformance":   "not reviewed",
            "osd_conformance":  "not reviewed",
            "status":           "active",
            "title":            "License Not Specified",
            "url":              ""
        },
        ...
    ]

Caching
-----------------------------------------------------

The ckanext-dcatdonl plugin caches the contents of the valuelists for up to 24 hours. On the first
request made after midnight each day, the cache will be invalidated and rebuild. This means that
any changes made to the contents of the valuelists can take up to 24 hours to take effect.
