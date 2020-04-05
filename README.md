# Magento 2 Questions Answer for Developer
### Use of search_request.xml
Magento 2 provides a declarative way to describe search request which should be executed. search_request.xml is a part of Query API. This declaration describes:

	--What index should be queried
	--What full-text queries should be executed (queries section)
	--What filters should be applied (filters section)
	--For which attributes faceted search should be built (Layered Navigation in terms of Magento) (aggregations section)

Naming convention here is very similar to ElasticSearch. For example, if you will look at XSD file (Search/etc/search_request.xsd) you will see that there are three possible query types:

	--Bool Query (analogue for Elasticsearch BoolQuery)
	--Match Query (analogue for Elasticsearch Match Query)
	--Filter Query (analogue for Elasticsearch Filtered Query)
	--There is presentation which describes Magento 2 new Search approach and architecture

For now Magento indexes just product data. And there are 3 scenarios (read 3 search queries for that data):

	--Quick Search (<request query="quick_search_container" index="catalogsearch_fulltext">)
	--Advanced Search (<request query="advanced_search_container" index="catalogsearch_fulltext">)
	--Category View (<request query="catalog_view_container" index="catalogsearch_fulltext">). As Magento implies Category View scenatio - as a search query without full text query in it.


---

[![Alt text](https://www.kashyapsoftware.com/pub/media/logo/stores/1/ks_logo.png "kashyapsoftware.com")](https://www.kashyapsoftware.com/)

