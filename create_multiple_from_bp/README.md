
This project will create a Create Multiple applications on ravello based on a Blueprint.
it can also:
- Generate individual guess token for each applications
- Generate an ansible inventory file that contains all VMs from all applications
- Collect all FQDN, IP addresses and user portal URL

##  Requirements

### On your laptop / server
The only requirement is to have Docker installed

### on Ravello
You must have an existing Blueprint on Ravello. The name of the blueprint is defined on the inventory file `inventory.ini`.

### inventory file
The name of the devices in the inventory file must match the name of the devices in the blueprint you want to duplicate.

# Define Ravello Credentials

You must define your ravello Credentials with the variables `ravello_login_username` and `ravello_login_password`.   
You can define them either in the inventory file or in any variables files

# Define how many applications you want to create

The name and the number of applications you will create is defined in the variable file `app_list.yaml`. By default, 3 applications will be created: `bob`, `alice` and `joe`.

```yaml
ravello_app_list:
  - app_name: bob
  - app_name: alice
  - app_name: joe
```

# Get started

Create the topologies on Ravello from the Blueprint
```
make create
```

Deploy the applications on AWS and setup the expiration time(do not start them)
```
make deploy
```

Generate an Ansible inventory file with all devices. *see below an example of inventory file*
```
make inventory
```

Download FQDN of each VMs
```
make fqdn
```

Generate Token for each applications and download user portal URL. *see below an example of url file generated*
```
make token
```


## Generated Inventory File

```ini
[spine1]
spine1-joe-1r2rnnkc.srv.ravcloud.com
spine1-alice-jvrdqxsv.srv.ravcloud.com
spine1-bob-c7qy2sjs.srv.ravcloud.com
[spine2]
spine2-joe-dhaguvz2.srv.ravcloud.com
spine2-alice-eylj5ydo.srv.ravcloud.com
spine2-bob-ad9p9zps.srv.ravcloud.com
[leaf1]
leaf1-joe-peqewkow.srv.ravcloud.com
leaf1-alice-iym5pspr.srv.ravcloud.com
leaf1-bob-vz0n8khk.srv.ravcloud.com
[leaf2]
leaf2-joe-4prillqx.srv.ravcloud.com
leaf2-alice-7ch0mk7q.srv.ravcloud.com
leaf2-bob-powjowjg.srv.ravcloud.com
[leaf3]
leaf3-joe-ss9h26lb.srv.ravcloud.com
leaf3-alice-dbqnd9mf.srv.ravcloud.com
leaf3-bob-7fujw2ly.srv.ravcloud.com
```

## Generated URL File

```yaml
bob: https://access.ravellosystems.com/simple/#/uHuf5CJgYl0jBeX4mpNdJMIConWcGAItv60Cd23vqyXvW4LyhWKTIJ1nq7SyQKgO/apps/78546273
alice: https://access.ravellosystems.com/simple/#/8FXPlY8g0STQzIpSOP7lJl51rUinIi0bP6wqJceOhoqbpsADrmPdy2z8pfDA4YHr/apps/78513359
joe: https://access.ravellosystems.com/simple/#/EJhcGsGJZjA9fYVIaY7gMGEDnmyY51qDhtrjMJEHDR1VxDDkZ7roagUOO7tzkyFY/apps/78513360
```
