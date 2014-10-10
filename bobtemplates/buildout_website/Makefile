#!/usr/bin/make
#
all: run

bootstrap.py:
	wget http://downloads.buildout.org/2/bootstrap.py
	touch $@

bin/python:
	virtualenv-2.7 .
	touch $@

buildout.cfg:
	ln -s dev.cfg buildout.cfg
	touch $@

bin/buildout: bin/python bootstrap.py buildout.cfg
	./bin/python bootstrap.py

.PHONY: buildout
buildout: bin/buildout
	bin/buildout -Nt 5

.PHONY: instance
instance: buildout
	./bin/instance1 fg

.PHONY: cleanall
cleanall:
	rm -fr develop-eggs downloads eggs parts .installed.cfg lib include bin buildout.cfg .mr.developer.cfg

.PHONY: prod
prod: 
	if test -f buildout.cfg;then rm -f buildout.cfg;fi
	if ! test -f buildout.cfg;then ln -s prod.cfg buildout.cfg;fi
	make buildout
