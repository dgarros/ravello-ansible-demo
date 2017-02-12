
This project will create a spine-leaf topology on Ravello using vqfx-lite (no-pfe)

##  Requirements

### On your laptop / server
The only requirement is to have Docker installed

### on Ravello
You must have an active ravello account and have uploaded an image of vqfx10k-re.  
The vqfx image must be named `vqfx10k-re-15.1X53-D60`

> you can [request access to a vqfx image here](http://www.juniper.net/us/en/dm/free-vqfx-trial/)

# Define Ravello_credential

You must define your ravello Credential with the variables `ravello_login_username` and `ravello_login_password`.   
You can define them either in the inventory file or in any variables files
