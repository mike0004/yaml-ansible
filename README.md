## yaml-ansible
This is a sampling of yaml experiments working with and without Ansible to test capabilities and see how the YAML translates.

**NOTE:** YAML version is 1.1, that's what Ansible wants.

It's beneficial to `brew install node` and `npm install -g js-yaml` to use this.

### Useful aliases:
```sh
alias jsonpp='python -m json.tool'
alias jsontoyaml='ruby -ryaml -rjson -e "puts YAML.dump(JSON.parse(STDIN.read))"'
alias yamltojson='ruby -rjson -ryaml -e "puts JSON.pretty_generate(YAML.load(STDIN.read))"'
```

### Example using js-yaml
if parsing fails, error message shown else the yaml is output in json
```sh
js-yaml yaml_vars_demo.yml
```

### I like to see how YAML transforms back (uses the aliases above)
```sh
js-yaml yaml_vars_demo.yml | jsontoyaml
```

### Running with the playbook
This is noted at the header of [playbook.yml](../master/playbook.yml)
```sh
# run the playbook on localhost (that's what "," yields)
ansible-playbook -i "," playbook.yml -v
```

## See also
- [YAML Spec 1.1](http://yaml.org/spec/1.1/)
- [Ansible YAML Basics](http://docs.ansible.com/ansible/YAMLSyntax.html)
