

DOCKER_RAVELLO = docker run -t -i -v $(shell pwd):/project juniper/ravello-ansible
DOCKER_JUNOS = docker run -t -i -v $(shell pwd):/project juniper/pyez-ansible:latest
OPTS ?= --limit=all

all:
		$(DOCKER_RAVELLO) ansible-playbook -i inventory.ini pb.rav.create_apps.yaml $(OPTS)

create:
		$(DOCKER_RAVELLO) ansible-playbook -i inventory.ini pb.rav.create_apps.yaml --tags=create $(OPTS)

deploy:
		$(DOCKER_RAVELLO) ansible-playbook -i inventory.ini pb.rav.create_apps.yaml --tags=deploy $(OPTS)

fqdn:
		$(DOCKER_RAVELLO) ansible-playbook -i inventory.ini pb.rav.create_apps.yaml --tags=fqdn --forks=1 $(OPTS)

token:
		$(DOCKER_RAVELLO) ansible-playbook -i inventory.ini pb.rav.create_apps.yaml --tags=token --forks=1 $(OPTS)

inventory:
		$(DOCKER_RAVELLO) ansible-playbook -i inventory.ini pb.rav.create_apps.yaml --tags=inventory --forks=1 $(OPTS)
