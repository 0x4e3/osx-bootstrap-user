# osx-bootstrap-user

The role to configure user environment.

[![Build Status](https://travis-ci.org/0x4e3/osx-bootstrap-user.svg?branch=master)](https://travis-ci.org/0x4e3/osx-bootstrap-user)

## Requirements

You should have ```homebrew``` installed.

## Role Variables

* ```user_use_oh_my_zsh``` -- default is ```true```
* ```oh_my_zsh_theme``` -- default is ```bira```
* ```oh_my_zsh_plugins``` -- list of plugins; default is ```[]```
* ```oh_my_zsh_case_sensitive``` -- default is ```false```
* ```oh_my_zsh_disable_update_prompt``` -- default is ```false```
* ```oh_my_zsh_disable_auto_update``` -- default is ```true```
* ```oh_my_zsh_update_days``` -- default is ```7```
* ```oh_my_zsh_disable_ls_colors``` -- default is ```false```
* ```oh_my_zsh_disable_auto_title``` -- default is ```false```
* ```oh_my_zsh_disable_correction``` -- default is ```true```
* ```oh_my_zsh_completion_waiting_dots``` -- default is ```false```
* ```oh_my_zsh_disable_untracked_files_dirty``` -- default is ```true```
* ```oh_my_zsh_hash_directories``` -- list of directories for hashing (ex. ```projects=~/Projects```); default is ```[]```
* ```oh_my_zsh_aliases``` -- list of aliases (ex. ```zshconfig="vim ~/.zshrc"```); default is ```[]```
* ```user_exports``` -- list of custom user exports (ex. ```PATH="/usr/local/sbin:$PATH"```); default is ```[]```
* ```user_use_pyenv``` -- default is ```true```

## Dependencies

[0x4e3.osx-bootstrap-homebrew](https://galaxy.ansible.com/0x4e3/osx-bootstrap-homebrew/).

## Example Playbook

```playbook.yml```:
```yml
---
- host: localhost
  vars_files:
    - vars/user.yml
  roles:
    - 0x4e3.osx-bootstrap-user
```

```vars/user.yml```
```yml
user_exports:
- PATH="/usr/local/sbin:$PATH"

oh_my_zsh_plugins:
- osx
- man
- colored-man
- brew

oh_my_zsh_hash_directories:
- projects=~/Projects

oh_my_zsh_aliases:
- zshconfig="vim ~/.zshrc"
- zshupdate="source ~/.zshrc"
```

## License

BSD
