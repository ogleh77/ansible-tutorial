Insha Allah 

Kadib marka aad hosts kaga siinayso pem secret key ga u move garee secret keygaga .ssh folderka beacuse downloads ka waxa ku qabsan kara security kadibna

ma yelayo inuu ku xidhidhsamo remote serverkaga  adigoo isticmalaya commandkan hoose

[servers]
13.234.114.29 ansible_user=ubuntu ansible_ssh_private_key_file=/Users/mohamedogleh/.ssh/my-server-key-pair.pem


Marka aad run garaynayso commandka sidan u isticmaal adiga oo dhex jooga folderka uu ku keydasan yahy configuration files kaagu

ansible-playbook --inventory inventory/vm-setup-playbook/hosts vm-setup-playbook.yml 


KNOW!!! HADDII KU RUN GAROOBI WAAYO PLAYBOOK KA MAIN KU HUBI FOLDER STRUCTURE KA

folder structure ku waa case sensitive 

waxa ka wadaa python/task iyo python/tasks isku mid mha


CREATE FILE AND WRITE TEXT INSIDE OF IT 

- name: shell module
  shell: echo "Asc world" > ./greeting

DELETE GREET FILE 

- name: delete file greeting 
  file: 
    path: ./greeting
    state: absent 

- SHELL MODULE WITH VARIABLES

- name: shell module
  vars:
  message: "Asc dadkoow"
  shell: echo {{message}} >  greet


ANSIBLE FILE MODULE

create multiple directories using loop

- name: Create multiple directories in a loop
  file:
  path: ./test/{{item}}
  state: directory
  loop:
    - test-1
    - test-2
    - test-3


SET THE DIRECTORY PERMISSIONS and OWNERS

- name: Create multiple directories in a loop
  file:
    path: ./test/{{item}}
    state: directory
    owner: ogleh
    group: group-blah
    mode: 0755
  become: true

    
CREATE FILE IF NOT EXIST 

- name: create file if not exist
  file:
    path: ./greet
    state: touch


REMOVE MULTIPLE FILES 

- name: remove multiple files
  file:
  path: ./{{item}}
  state: absent
  loop:
  - file-1
  - file-2
  - file-3