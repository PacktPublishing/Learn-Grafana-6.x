
run-es:
	docker-compose up elasticsearch

run-grafana:
	docker-compose up grafana

INDEX=airquality

es-describe:
	curl -XGET localhost:9200/$(INDEX)/_mapping?pretty

es-query:
	curl -XGET http://localhost:9200/$(INDEX)/_search?pretty

es-clean:
	curl -X DELETE "localhost:9200/$(INDEX)?pretty"
