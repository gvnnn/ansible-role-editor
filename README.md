gvnnn.editor
============

Installs and configure Neovim

Requirements
------------

None

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

    editor_packpath: "{{ lookup('env', 'HOME') }}/.local/share/nvim/site/pack"

Path plugins are cloned to and read from. See `:set runtimepath?` in Neovim.

    editor_init_template: init.vim.j2

To provide your own init file place it inside a `template/` directory at the playbook level and override this variable with the template name. e.g.:

    mkdir templates
    echo "set nocompatible" >> templates/myinit.vim.j2
    echo "editor_init_template=myinit.vim.j2" >> vars/main.yml  # ensure to set vars_files accordingly in your playbook

Dependencies
------------

None

Example Playbook
----------------

    - hosts: workstation
      roles:
         - { role: gvnnn.editor, editor_init_template: "myinit.vim.j2" }

License
-------

MIT
