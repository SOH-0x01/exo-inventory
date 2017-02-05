exo-inventory
=======

An ansible dynamic inventory based on the cloudstack example.  
It is customized for Exoscale with some opiniated decision on the group to create.

- Exoscale is a Switzerland cloud provider for the digital native based on the Apache Cloudstack API.
- Cloudstack is open source software designed to deploy and manage large networks of virtual machines.
- Ansible is the simplest way to automate apps and IT infrastructure, the DevOps way.


**Specificities**

- The inventory will create host groups based on some of your vm tags. You can adjust the list of tags you want to generate a group by modifying the  *GROUP_TAGS* list.
```python
# List of tags to be used for groups
self.GROUP_TAGS = ['env','cluster_name','cluster_role']
```

- The inventory will also guess the *ansible_user* and *ansible_python_interpreter* based on the tamplate of the vm.



Getting Started
=======

First copy or create your cloudstack.ini with your exoscale credentials.

```
$ cat ./cloudstack.ini
[cloudstack]
endpoint = https://api.exoscale.ch/compute
key = cloudstack api key
secret = cloudstack api secret
method = post
```

Test the listing, it should display all your instances.
```
& ./cloudstack.py --list
```


Authors
=======
Marc Guillen (marc.guillen@datsci.farm

Licence
=======
GNU
Click on the [Link](COPYING) to see the full text.
