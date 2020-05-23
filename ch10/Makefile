APPS := grafana loki promtail prometheus

build:
	docker-compose pull

up:
	docker-compose up -d

down:
	docker-compose down

start:
	docker-compose start

stop:
	docker-compose stop

build-%:
	docker-compose pull $*

up-%:
	docker-compose up -d $*

start-%:
	docker-compose start $*

stop-%:
	docker-compose stop $*

test-loki:
	curl -XGET http://localhost:3100/ready

test-promtail:
	curl -XGET http://localhost:9080/ready