# makefile
SHELL := /bin/bash

run:
	make precommit
	python manage.py runserver 0.0.0.0:8000

precommit:
	black --line-length=140 .
	flake8 --ignore E501
