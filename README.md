# Modify iptables with ansible

this code is able to modify iptables rules in group of servers permanently and easy.
 


## Features

- modify based on chain in any tables without effecting other rules
- put rules in different text files and set on iptables
- make iptables rules permanent 



## Documentation

put all rules in files directory with same chain in txt file with structure bellow:
```bash
files/<TABLE_NAME>/<CHAIN_NAME>.txt
```

* Put complete rules in every chain file. forexample if you want to update or add rules with chain INPUT in filter table: 1. this code delete all INPUT rules in filter table in existing iptables and add all rules in INPUT.txt file and make it permanent
* If you do not want to change any rules with specefic chain in each table just do not create text file in ansible. this code does not change any rules in iptables if files/<TABLE_NAME>/<CHAIN_NAME>.txt does not exists
* Put group of servers address in inventories/hosts file 
* Do not forget install ansible and make them reachable by ansible server through ssh. you can check by 
```bash 
ansible all -m ping 
```
* If you want to flush any table with specefic chain just create <CHAIN_NAME>.txt empty and run ansible
* this ansible execute just in debian based operating systems

## Installation

Install my-project with ansible-playbook

```bash
  ansible-playbook -i inventories/hosts execute.yml
```

   
