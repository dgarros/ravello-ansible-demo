

DOCKER_RAVELLO = docker run -t -i -v $(shell pwd):/project juniper/ravello-ansible
DOCKER_JUNOS = docker run -t -i -v $(shell pwd):/project juniper/pyez-ansible:latest

create:
		$(DOCKER_RAVELLO) ansible-playbook -i inventory.ini pb.rav.create.yaml

deploy:
		$(DOCKER_RAVELLO) ansible-playbook -i inventory.ini pb.rav.deploy.yaml

fqdn:
		$(DOCKER_RAVELLO) ansible-playbook -i inventory.ini pb.rav.get_fqdn.yaml

delete:
		$(DOCKER_RAVELLO) ansible-playbook -i inventory.ini pb.rav.delete.yaml

get-version:
		$(DOCKER_JUNOS) ansible-playbook -i inventory.ini pb.junos.show_version.yaml
