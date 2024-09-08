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