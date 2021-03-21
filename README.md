# What
Ansible playbook for setting up symbol node

## Prerequisite
- ansible in host machine
- target OS is ubuntu18.04

### Host machine
- Please follow [this step](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)
- Run command below 

```
ansible-galaxy install geerlingguy.swap
```

### Guest machine
- Check if it can be accessed with SSH.

## Prepare config file 
- Copy sample config file by command below, then modify it for your machine.

```
cp config-sample.yml config.yml
```

- Set config parameters to yours

## Command

- From host machine for setting up guest machine

```
ansible-playbook -i hosts.yml playbook.yml
```

- In guest machine, confirm working correctly.

```
# if docker-compose not found
symbol-bootstrap config -a dual
symbol-bootstrap compose

symbol-bootstrap healthCheck
curl http://localhost:3000/node/info
curl http://localhost:3000/chain/info
```
 
## References 

参考にさせていただきました、ありがとうございます。

```
https://nemlog.nem.social/blog/50604
https://qiita.com/curupo/items/12357755b9ac0a23ae22
https://nemlog.nem.social/blog/49345
https://gist.github.com/mattiaslundberg/ba214a35060d3c8603e9b1ec8627d349
```

[preset example](https://github.com/nemtech/symbol-bootstrap/blob/main/docs/presetGuides.md)