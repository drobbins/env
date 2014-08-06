.PHONY: facts hello

vagrant_inventory = .vagrant/provisioners/ansible/inventory/vagrant_ansible_inventory
vagrant_keyfile = ~/.vagrant.d/insecure_private_key

facts:
	ansible                              \
		-i $(vagrant_inventory)          \
		all                              \
		--private-key=$(vagrant_keyfile) \
		-u vagrant                       \
		-m setup

hello:
	ansible                              \
		-i $(vagrant_inventory)          \
		all                              \
		--private-key=$(vagrant_keyfile) \
		-u vagrant                       \
		-a "echo Hello World"

%.yml.out: %.yml
	ansible-playbook                     \
		$<                               \
		-i $(vagrant_inventory)          \
		--private-key=$(vagrant_keyfile) \
		-u vagrant
