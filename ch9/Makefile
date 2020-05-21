IMAGE=sensors
INDEX=cpu_metrics

build:
	docker-compose pull grafana

up:
	docker-compose up -d grafana

down:
	docker-compose down

start:
	docker-compose start grafana

stop:
	docker-compose stop grafana

restart:
	docker-compose restart grafana

clean:
	docker-compose rm -vs

build-logstash:
	docker-compose pull logstash

up-logstash:
	docker-compose up -d logstash

build-elasticsearch:
	docker-compose pull elasticsearch

up-elasticsearch:
	docker-compose up -d elasticsearch

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

run-powermetrics:
	sudo powermetrics -i 60000 --format plist --samplers smc -u data/sample.plist
