we have created the Gloden AMI using Packer using  inside docker VM


Please find the command below to execute the in local:

1. setup smal2aws account in local

https://skechers.atlassian.net/wiki/spaces/CLOUDOPS/pages/1912078349/How+to+Connect+to+AWS+Using+Terminal

2. clone the repo into local
3. cd to packer folder
4.  Validated the packer.json file using below command:

packer validate packer.json [make sure packer is installed in local]
5. run the packer build to create AMI
packer build packer.json



6. Step to run Packer via Jenkins

a.  Navigate to Jenkins Job : https://jenkins.skechers.com/job/packer_ami/job/masterb. 
b. build the Job
c. check the console out for AMI image ID.
