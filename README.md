# efs
Mounting an EFS on multiple ec2-instances EFS Share and EBS Volume is the name for both usage <br/>
EFS is a file level storage, which can be attached to multiple instances at a time, but EBS instances can only be attached to a single instance at a time.<br/>
EBS can be considered as a harddisk while EFS can be considered as a shared folder. EBS Max size is 16TB and EFS size is 8 Exabyte ( 1000 Petabytes ). <br/>
Billing is calculated on amount of data stored while EBS billing is calculated on the entire disk used. <br/>

# Creating an Elastic File system
create filesystem > Name : docroot <br/>
VPC, Customize <br/>
Storage class : Standard ( where the data is stored on minimum 3 Datacenters ) , Onezone ( data is stored on a single DC ). <br/>
Disable auto backup <br/>
Lifecycle managment : This is used in case of large amount of data, consider data used on Netflix , Transition to IA to avoid unnecessary charges of data stored on Standard class ( 3 Az's). Infrequent tier is where data not constantly used are placed <br/>
Encryption is disabled <br/>
Performance settings : Where the communication between Ec2 and EFS ie the data exchange is mentioned, Bursting will only activate when need is there, enhanced will provide a dedicated Bandwidth.
Security group used in EFS should allow NFS port as this is the protocol used by EFS. (2049) 

# Create and Ec2 instance and prepare the Docroot and mount the EFS volume
