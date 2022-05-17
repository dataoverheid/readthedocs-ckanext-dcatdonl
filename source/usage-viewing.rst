Viewing a dataset or resource
============================================

When viewing a dataset or resource of a CKAN installation running the ckanext-dcatdonl extension
additional fields will be shown to the consumer. These additional properties are in line with the
schema provided in the CKAN Schema chapter of this documentation.

data.overheid.nl
--------------------------------------------

Data.overheid.nl maintains several additional properties for datasets that may be encountered when
viewing datasets and resources. These properties are detailed below:

Dataset.duplicate_resources
    States which resources have duplicates on data.overheid.nl
Resource.link_status
    States if the given download or accessUrl is available for consumption
Resource.link_last_checked_date
    States when the link_status was last updated
Resource.is_duplicate_of
    States the resource id that is a duplicate of this resource