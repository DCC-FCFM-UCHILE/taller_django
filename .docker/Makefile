# makefile

build:
	docker-compose --file dc-produccion.yml --project-name taller_django up -d --build --force-recreate --remove-orphans
	docker ps

restart:
	docker restart taller_django
	docker ps

update:
	git stash
	git pull
	git stash pop

static:
	docker exec taller_django python manage.py collectstatic --no-input

# loaddata:
# 	docker exec taller_django make loaddata

# backup:
# 	docker exec taller_django make backup

media:
	sudo cp -r ../media/* /home/instalar/media/taller_django

migrate:
	docker exec taller_django python manage.py migrate

ssh:
	docker exec -it taller_django bash

deploy:
	make update
	make build
	make migrate
	# make loaddata
	make static
	make media
	make restart

_secret:
	./app/secret.sh

__media:
	sudo cp -r ../media/* /home/instalar/media/taller_django/