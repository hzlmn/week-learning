## ElasticSearch
> Tips related to elasticsearch learning


#### Detele all indices except one

```shell
$ curl -XDELETE http://elastic:9200/index-*,special-index*
```