Schema validation
==================================================================================================

Outlined below are the possible validation messages that the ckanext-dcatdonl plugin can generate 
based on the input it is given. The standard CKAN validation messages are not included in this 
documentation.

Validation messages
--------------------------------------------------------------------------------------------------

website, email or phone is required for the contact_point
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This error occurs when the given dataset does not contain a value for either
:code:`contact_point_website`, :code:`contact_point_email` or :code:`contact_point_phone`. Atleast
one of these three properties must be provided in order for the dataset to be considered valid.

when hash is provided, has_algorithm must too be provided
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
when hash_algorithm is provided, hash must too be provided
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This error occurs when either the property :code:`hash` or :code:`hash_algorithm` is present, but
its counterpart is not. When either is provided, both are required.

legal_foundation_ref must be provided when providing any of the legal_foundation_* properties
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
legal_foundation_uri must be provided when providing any of the legal_foundation_* properties
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
legal_foundation_label must be provided when providing any of the legal_foundation_* properties
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

When any of the legal_foundation_* properties is given, all are required.

spatial_value cannot be validated without a corresponding spatial_scheme
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
spatial_scheme must be accompanied by a spatial_value
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

These errors may occur when the request body contains a :code:`spatial_scheme` but not a 
:code:`spatial_value` or vice versa. Both properties are required to provide spatial metadata. To 
resolve this, provide both properties in the request body.

Spatial validation
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
This complex validator spans the fields :code:`spatial_scheme` and :code:`spatial_value`. Both
fields are optional. However when one is provided, the other must too be provided. Furthermore the
value of :code:`spatial_scheme` determines the validator that will be used on :code:`spatial_value`.
In the table below the :code:`spatial_value` validators are shown for the possible values of
:code:`spatial_scheme`.

.. list-table::
    :widths: 65 35
    :header-rows: 1

    * - spatial_scheme (base=http://standaarden.overheid.nl)
      - spatial_value validation
    * - /owms/4.0/doc/waardelijsten/overheid.gemeente
      - Required, String, From overheid:spatial_gemeente
    * - /owms/4.0/doc/waardelijsten/overheid.koninkrijksdeel
      - Required, String, From overheid:spatial_koninkrijksdeel
    * - /owms/4.0/doc/waardelijsten/overheid.provincie
      - Required, String, From overheid:spatial_provincie
    * - /owms/4.0/doc/waardelijsten/overheid.waterschap
      - Required, String, From overheid_spatial_waterschap
    * - /owms/4.0/doc/syntax-codeerschemas/overheid.epsg28992
      - Required, String, Regex match :code:`^\d{6}(\.\d{3})? \d{6}(\.\d{3})?$`
    * - /owms/4.0/doc/syntax-codeerschemas/overheid.postcodehuisnummer
      - Required, String, Regex match :code:`^[1-9]\d{3}([A-Z]{2}(\d+(\S+)?)?)?$`

So when a list of spatial schemes is provided, e.g.

.. code-block:: json

    [
        "http://standaarden.overheid.nl/owms/4.0/doc/waardelijsten/overheid.gemeente",
        "http://standaarden.overheid.nl/owms/4.0/doc/waardelijsten/overheid.waterschap"
    ]

Then the values in the list of :code:`spatial_value` must be values validate against the validators
defined in the table above. In this example the values must either be values of the valuelist
:code:`overheid:spatial_gemeente` or values of the valuelist :code:`overheid:spatial_waterschappen`.

value [{{ value }}] is not a valid spatial according to the schemes provided
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This error occurs when one of the values of the :code:`spatial_value` property does not validate
against the schemas provided in the :code:`spatial_scheme` property. To correct this, either update
the :code:`spatial_value` or the :code:`spatial_scheme` values so that they are in sync.

value must be a valid date (yyyy-mm-ddThh:mm:ss)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This error occurs when the temporal metadata is provided in the wrong datetime format. Ensure that
all temporal metadata is provided in the :code:`yyyy-mm-ddThh:mm:ss` format, e.g.
:code:`2017-12-31T13:15:00`.

temporal_start cannot be greater or equal to temporal_end
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
temporal_end cannot be smaller or equal to temporal_start
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

These errors occur when providing illegal temporal data. To resolve this, provide temporal data
where the :code:`temporal_start` property contains a date that is smaller than the date provided in
:code:`temporal_end`.

value must be a string
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
value must be a list
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
value must be a dictionary
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

These errors occur when providing the wrong datatype for a specific value. To resolve these errors
the right datatype must be provided.

value is not a valid uri
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This error occurs when an uri string is expected. To resolve this, provide a valid http uri.

only one license can be provided, list given
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This error occurs when a list of licenses is provided. Only one license can be provided for a
dataset or resource.

value must have a id property
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This error occurs when the dictionary provided for the license property does not contain the key
:code:`id`. The license dictionary provided must have a :code:`id` property to validate the given
license.

no matching license id found for given value
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This error occurs when the license id provided is not part of the list of valid licenses. Consult
the license valuelist at {{ URL }} for the supported licenses.

value [{{ value }}] is not a valid {{ valuelist }}
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
This error occurs when providing values that are not part of the given valuelist. Consult the given
valuelist to see the acceptable values.

values do not meet the minimum requirements
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
values do not meet the maximum requirements
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

These errors occur when providing too little or too many values in a given list for a given
property. Consult the schema defined in 'CKAN Schema' chapter of this documentation for the
expectations of the amount of values.

values must be unique
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This error occurs when the list of values provided contains duplicates. Remove the duplicates to
resolve this error.
