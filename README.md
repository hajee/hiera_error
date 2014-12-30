# Show the inconsistency on using hiera functions


## Start the vagrant box

```sh
$ vagrant up 
```

# log in as root 

```sh
$ vagrant ssh
Last login: Tue Dec 30 22:55:44 2014 from 10.0.2.2
$ sudo su -
$ cd /vagrant
$ puppet apply pass_1.pp
Notice: Compiled catalog for demo.example.com in environment production in 0.05 seconds
Notice: Finished catalog run in 0.01 seconds
$ puppet apply pass_2.pp
Notice: Compiled catalog for demo.example.com in environment production in 0.05 seconds
Notice: Finished catalog run in 0.01 seconds
$ puppet apply fail.pp
Error: Could not find data item value in any Hiera data file and no default supplied at /etc/puppet/modules/test/manifests/test_define.pp:1 on node demo.example.com
Error: Could not find data item value in any Hiera data file and no default supplied at /etc/puppet/modules/test/manifests/test_define.pp:1 on node demo.example.com
```