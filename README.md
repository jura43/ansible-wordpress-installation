# Ansible Wordpress Installation

## Introduction
This is repo is result of project on Advanced DevOps course. It consists Ansible playbooks for installing Wordpress site with some additional configuration. For completing this project I created CentOS 8 virtual machine with additional disk and additional network adapter with separate network that is used to connect to VM from workstation. Each task is in separate playbook named according to the task they complete.
 
## Tasks
These are the tasks that were defined in project

 1.  Check for available updates to the VM and if they exist list them. Update all packages to the latest version.
 2.  Create two users with the details from the users.txt file.
 3.  Install  the  LAMP stack by using PHP7. Install  the  PHP modules listed in  the  task_3.txt file.
 4.  Configure banner and motd files on test VM using file task_4_banner.j2 and task_4_motd.txt
 5.  Install PHP 7 and configure PHP configuration files in  the  default  configuration  directory
 6.  Configure firewalld to set the public interface to  the  public zone. It should allow services mysqld, http and https.
 7.  Configure firewalld  to allow public IPs  with /32 prefix  from task_7.txt to access  the public interface.
 8. Configure  the  second disk to be added to a volume group with a custom name, with a logical volume using  the  max capacity of the volume group. Logical volume should be mounted to /var/www/html. All the  data about LVM configuration should be  passed to the playbook through a file called vars.yaml you will create (VG name, LVM  name, directory name, permissions, SELinux context).
 9. Install MySQL and create two users db_admin and  wordpress. Grant them all permissions and set passwords for them and for the root user. Passwords should be stored inside a vault file you create and encrypt with password  redhat. User names should be passed in from a task_9_users.txt file you will create.
 10. Create a role  that  will test if all the components  configured in the previous steps  are working and are configured correctly. *(Not solved)*
 11. Create a role  that  will install WordPress and redis. WordPress should be stored in /var/www/html.  The owner of that directory should be apache. Directory permissions, ACLs and default ACLs  should reference  the  apache user as the owner.  Redis should be configured with maxmemory 256mb and  maxmemory-policy allkeys-lru.  A hash key called  student  should be created in redis  with two fields name and surname containing your name and surname.

## Requriements
To run this playbook you need to have installed Anisble, Python 3 and pymysql library for Python.

    ansible-playbook playbook.yml --ask-vault-password
