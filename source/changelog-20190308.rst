Changes applied on 08/03/2019
============================================

- Introduced a new property to CKAN :code:`Dataset` schema: :code:`national_coverage`. This property is an optional boolean. When this property is not present in a dataset it is considered 'false'.
- Introduced :code:`national_coverage` to Solr schema.
- Introduced facet field :code:`facet_national_coverage` to Solr schema. 