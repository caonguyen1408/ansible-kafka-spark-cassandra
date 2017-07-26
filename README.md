## Ansible Provisioning EC2 hosts

**Usage:**

Conatain 4 variables file using *ec2_vars/*.*.yml* as a template.

AnalyticUI & have 3 instance types for 3 role:

- MariaDB: webservers-instance

- MongoDB: mongodb-instance

- Web server: webservers-frontend-instance,
	      webservers-api-instance

### AIM Information ###

Region: us-west-2

 - ami-b0d85fd0 (MariaDB)

 - ami-eed95e8e (MongoDB)

 - ami-4ee7602e (Web Analytic API)

 - ami-b2b334d2 (Web html & dashboard)

Region: ap-southeast-1 

 - ami-dc47f0bf (MariaDB)

 - ami-b145f2d2 (MongoDB)

 - ami-5045f233 (Web Analytic API)

 - ami-e6209785 (Web html & dashboard)



After setting all variables, run it:
cp hosts.sample hosts

    ansible-playbook -i hosts -e "type=webserver-frontend-instance" provision-ec2.yml
    ansible-playbook -i hosts -e "type=webserver-api-instance" provision-ec2.yml
    ansible-playbook -i hosts -e "type=mariadb-instance" provision-ec2.yml
    ansible-playbook -i hosts -e "type=mongodb-instance" provision-ec2.yml