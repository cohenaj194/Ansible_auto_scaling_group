# Ansible_auto_scaling_group

Ansible playbook that creates an auto scaling infastructure in aws. 

Before running put your ami keys in `amiKeys.yml` replacing the current info:

    ---

    ami_access: "GFGHDSFSSDFGHKKDQgibberish"
    ami_secret: "jkfasdfadflhKJadsadHDLFHDHisdf//+sgibberish"

Then encrypt it with:

    ansible-vault encrypt amiKeys.yml

Then replace the info in `regionInfo.yml` with the info of your aws project:

    ---
    #your keypair
    keypair: "someKeyPairName"
    #your security group
    group: "sg-asd34f3e"
    #the subnet you want to use, found in the vpc menu
    subnetID: "subnet-adsfa243223"
    #the region of the subnet you are using
    regi: "us-east-1"



Run with

    ansible-playbook autoscale.yml --ask-vault-pass

