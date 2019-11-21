IMAGE=weather
DB=weatherdb
TEMPFILE=wx.txt
STATIONS=KSFO,KDEN,KSTL,KJFK

docker:
	docker-compose up -d

build:
	docker build --pull --tag $(IMAGE) .

drop:
	docker run --network=host $(IMAGE) --drop --db $(DB)

dump:
	docker run --rm --network host -v "$$(PWD):/usr/src/app" $(IMAGE) --output $(TEMPFILE) --stations $(STATIONS)

load:
	docker run --rm --network host -v "$$(PWD):/usr/src/app" $(IMAGE) --input $(TEMPFILE) --db $(DB)

reload: dump load

full-reload: drop dump load

