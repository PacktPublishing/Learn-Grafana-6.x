IMAGE=sensors
INDEX=cpu_metrics

run-es:
	docker-compose up elasticsearch

run-grafana:
	docker-compose up grafana

run-logstash:
	docker-compose up logstash

es-describe:
	curl -XGET localhost:9200/$(INDEX)/_mapping?pretty

es-query:
	curl -XGET http://localhost:9200/$(INDEX)/_search?pretty

es-clean:
	curl -X DELETE "localhost:9200/$(INDEX)?pretty"

docker-build:
	docker build --pull --tag $(IMAGE) .

docker-run:
	docker run --rm --network host -v "$$(PWD):/usr/src/app" $(IMAGE)
