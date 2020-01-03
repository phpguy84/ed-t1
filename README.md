Python and Ansible should be installed on the machine that you plan
to run this playbook from.

Steps to run the playbook:
1. clone this repo and `cd` inside
2. run `source envvars` (please make sure the paths in the file are correct as they depend on your current working environment)
3. set the ip address of your MariaDB VM in the `inventory` file
4. run the playbook `ansible-playbook -u root -i inventory site.yml -v` (you need to specify a remote user, in my case I did that on Digital Ocean and the user was `root`)

Testing the setup:
1. ssh into your new VM
2. `docker exec -it mariadb-instance bash`
3. `mysql -u zamro -p` (provide the password from the test task description)

All the credentials are in the Ansible vault file. They are encrypted. For the sake of this current assesment I put the vault password along with the repo (you can find it in the vault.txt). In real systems this is done differently of course.
