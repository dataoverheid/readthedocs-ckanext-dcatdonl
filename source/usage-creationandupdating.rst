Creating or updating datasets and resources
============================================

This extension adds several new mandatory and optional properties. A `Postman collection`_ is
available that includes examples on how to communicate with a CKAN installation that uses
ckanext-dcatdonl.

Below several examples are given on how to interact with CKAN.

Minimum dataset creation request
-------------------------------------------

:code:`(POST) {{CKAN_HOST}}/api/3/action/package_create`

.. code-block:: json

    {
        "owner_org":                "{{ORG_ID}}",
        "identifier":               "https://www.mijn.organisatie.nl/datasets/mijndataset1",
        "name":                     "mijndataset1",
        "title":                    "mijndataset1",
        "notes":                    "De omschrijving van mijndataset1!",
        "metadata_language":        "http://publications.europa.eu/resource/authority/language/NLD",
        "authority":                "http://standaarden.overheid.nl/owms/terms/'s-Hertogenbosch",
        "publisher":                "http://standaarden.overheid.nl/owms/terms/Centraal_Bureau_voor_de_Statistiek",
        "contact_point_name":       "John Doe",
        "license_id":               "http://creativecommons.org/licenses/by/4.0/deed.nl",
        "language":                 [
                                        "http://publications.europa.eu/resource/authority/language/NLD"
                                    ],
        "theme":                    [
                                        "http://standaarden.overheid.nl/owms/terms/Arbeidsomstandigheden_(thema)"
                                    ],
        "modified":                 "2018-04-11T09:00:00"
    }

Full dataset creation request
-------------------------------------------

:code:`(POST) {{CKAN_HOST}}/api/3/action/package_create`

.. code-block:: json

    {
        "owner_org":                "{{ORG_ID}}",
        "identifier":               "https://www.mijn.organisatie.nl/datasets/mijndataset1",
        "alternate_identifier":     [
                                        "https://www.cbs.nl/datasets/denbosch-mijndataset1"
                                    ],
        "language":                 [
                                        "http://publications.europa.eu/resource/authority/language/NLD"
                                    ],
        "source_catalog":           "https://data.overheid.nl",
        "authority":                "http://standaarden.overheid.nl/owms/terms/'s-Hertogenbosch",
        "publisher":                "http://standaarden.overheid.nl/owms/terms/Centraal_Bureau_voor_de_Statistiek",
        "contact_point_email":      "john.doe@cbs.nl",
        "contact_point_address":    "Straatnaam 12, 1234AB, Amsterdam",
        "contact_point_name":       "John Doe",
        "contact_point_phone":      "020 - 1234567",
        "contact_point_website":    "https://cbs.nl",
        "contact_point_title":      "",
        "access_rights":            "http://publications.europa.eu/resource/authority/access-right/PUBLIC",
        "url":                      "https://www.mijn.organisatie.nl/datasets/mijndataset1",
        "conforms_to":              [
                                        "https://standaarden.nl/mijn_standaard"
                                    ],
        "related_resource":         [
                                        "https://www.mijn.organisatie.nl/datasets/anderedataset12"
                                    ],
        "source":                   [
                                        "https://www.mijn.organisatie.nl/datasets/mijndataset0"
                                    ],
        "version":                  "1.0",
        "has_version":              [
                                        "https://www.mijn.organisatie.nl/datasets/mijndataset0"
                                    ],
        "is_version_of":            [
                                        "https://www.mijn.organisatie.nl/datasets/mijndataset2",
                                        "https://www.mijn.organisatie.nl/datasets/mijndataset3"
                                    ],
        "legal_foundation_ref":     "art-1",
        "legal_foundation_uri":     "http://wetten.nl/de-wet",
        "legal_foundation_label":   "De wet!",
        "frequency":                "http://publications.europa.eu/resource/authority/frequency/DAILY",
        "provenance":               [
                                        "https://www.mijn.organisatie.nl/datasets/uitleg"
                                    ],
        "sample":                   [
                                        "https://www.mijn.organisatie.nl/datasets/mijndataset1/samples"
                                    ],
        "license_id":               "http://creativecommons.org/licenses/by/4.0/deed.nl",
        "name":                     "mijndataset1",
        "title":                    "mijndataset1",
        "notes":                    "De omschrijving van mijndataset1!",
        "tags":                     [
                                        { "name": "mijn" },
                                        { "name": "dataset" },
                                        { "name": "een" },
                                        { "name": "Den Bosch" },
                                        { "name": "CBS" }
                                    ],
        "metadata_language":        "http://publications.europa.eu/resource/authority/language/NLD",
        "theme":                    [
                                        "http://standaarden.overheid.nl/owms/terms/Arbeidsomstandigheden_(thema)"
                                    ],
        "modified":                 "2018-04-11T09:00:00",
        "spatial_scheme":           [
                                        "http://standaarden.overheid.nl/owms/4.0/doc/waardelijsten/overheid.gemeente"
                                    ],
        "spatial_value":            [
                                        "http://standaarden.overheid.nl/owms/terms/'s-Hertogenbosch"
                                    ],
        "temporal_label":           "Jaar 2017",
        "temporal_start":           "2017-01-01T00:00:00",
        "temporal_end":             "2017-12-31T23:59:00",
        "dataset_status":           "http://data.overheid.nl/status/beschikbaar",
        "date_planned":             "2018-01-11T13:29:00",
        "high_value":               "True",
        "basis_register":           "False",
        "referentie_data":          "True"
    }

Minimum resource creation request
-------------------------------------------

:code:`(POST) {{CKAN_HOST}}/api/3/action/resource_create`

.. code-block:: json

    {
        "package_id":               "{{ PACKAGE_ID }}",
        "name":                     "myresource1",
        "url":                      "http://my.organization.com/mydataset/myresource1",
        "description":              "My dataset description",
        "metadata_language":        "http://publications.europa.eu/resource/authority/language/NLD",
        "format":                   "http://publications.europa.eu/resource/authority/file-type/ZIP",
        "language":                 "http://publications.europa.eu/resource/authority/language/NLD",
        "license_id":               "http://creativecommons.org/publicdomain/mark/1.0/deed.nl"
    }

Full resource creation request
-------------------------------------------

:code:`(POST) {{CKAN_HOST}}/api/3/action/resource_create`

.. code-block:: json

    {
        "package_id":               "{{ PACKAGE_ID }}",
        "name":                     "myresource1",
        "url":                      "http://my.organization.com/mydataset/myresource1",
        "description":              "My dataset description",
        "metadata_language":        "http://publications.europa.eu/resource/authority/language/NLD",
        "format":                   "http://publications.europa.eu/resource/authority/file-type/ZIP",
        "language":                 "http://publications.europa.eu/resource/authority/language/NLD",
        "license_id":               "http://creativecommons.org/publicdomain/mark/1.0/deed.nl",
        "linked_schemas":           "http://some.standard.nl/reference",
        "size":                     1234567890,
        "download_url":             "http://my.organization.com/mydataset/myresource1.zip",
        "mimetype":                 "https://www.iana.org/assignments/media-types/application/activity+json",
        "release_date":             "2017-12-31T15:16:00",
        "rights":                   "",
        "status":                   "http://purl.org/adms/status/Completed",
        "modification_date":        "2018-01-03T12:09:00",
        "hash":                     "dfuyhdf;lgkjlwwriyuwefhsdkf",
        "hash_algorithm":           "SHA1",
        "documentation":            "http://my.organization.com/mydataset/documentation"
    }

.. _Postman collection: https://www.getpostman.com/collections/c54a66d658d1dec274bb