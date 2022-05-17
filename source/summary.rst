Summary
========================================

This documentation describes the ckanext-dcatdonl plugin developed by Textinfo B.V. on behalf of
KOOP. This plugin implements the DCAT-AP-DONL 1.1 metadata standard into CKAN. DCAT-AP-DONL 1.1 is
a DCAT application profile based on the profile of DCAT-AP-NL 1.1, which itself is based on the
application profile of DCAT-AP-EU 1.1. It aims to reduce data duplications and to standardize
values wherever possible.

.. note::
    It is important to note that while this extension updates the schema of CKAN, it does not
    provide front-end templates for these extended schemas. Users of this extension with the desire
    for such templates need to implement those templates themselves in a separate plugin.

A modified version of this extension is currently used in the CKAN environment of the `Data.Overheid.nl`_ webapplication.
The most recent version of the public extension can be found on https://gitlab.textinfo.nl/opensource/ckanext-dcatdonl.

The following subjects are described

1. how to install the plugin into a existing CKAN installation
2. how to use the functionality the plugin introduces once it is installed
3. the modifications to the CKAN schema that the plugin is responsible for
4. the validation of this schema as defined by DCAT-AP-DONL 1.1
5. description of all the valuelists and their locations
6. the structure of the plugin code itself

Contact
--------------------------------------------

For questions and/or comments regarding this CKAN extension please contact KOOP(Kennis- en
Exploitatiecentrum Officiële Overheidspublicaties) via:

:Online:
    `koopoverheid.nl`_

:Email:
    `opendata@overheid.nl`_

:Telephone:
    \(070\) 7000 526

References
-------------------------------

- `Data.Overheid.nl`_
- `DCAT-AP-NL 1.1`_
- `DCAT-AP-DONL 1.1`_
- `CKANEXT-DCATDONL documentation`_
- `CKANEXT-DCATDONL repository`_

.. _koopoverheid.nl: https://www.koopoverheid.nl/
.. _gitlab.textinfo.nl/opensource/ckanext-dcatdonl/tree/public.version: https://gitlab.textinfo.nl/opensource/ckanext-dcatdonl/tree/public.version
.. _opendata@overheid.nl: mailto:opendata@overheid.nl
.. _Data.Overheid.nl: https://data.overheid.nl
.. _DCAT-AP-NL 1.1: http://dcat-ap-nl.nl
.. _DCAT-AP-DONL 1.1: https://dcat-ap-donl.readthedocs.io
.. _CKANEXT-DCATDONL documentation: https://ckanext-dcatdonl.readthedocs.io
.. _CKANEXT-DCATDONL repository: https://gitlab.textinfo.nl/opensource/ckanext-dcatdonl/
