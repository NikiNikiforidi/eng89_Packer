# Packer

HashiCorp tutorial:

https://learn.hashicorp.com/tutorials/packer/get-started-install-cli?in=packer/aws-get-started

<br> </br>


### Install packer and creating an enviroment variable 
- From link, in section **Install Packer** 
	- Download zip file
- Create file on computer to save packer.exe
<br> </br>
- Creating a PATH
	- Right clock on window icon -> System -> Adnaced system settings -> Environment Variables
	- Scroll down in system variables until you find PATH
	- Click edit and click New.
	- Copy/paste packer file path and press OK 
	<br> </br>
- To check if it has installed correctly
	- Open gitbash and enter `packer`, you should get a respons with packer information 
	<br> </br>
	- -----------------------------------------------
### Building an Amazon ec2 AMI with packer
- Create directory names packer_tutorial
	- `mkdir packer_tutorial`
- Navigate to directory 
- Create a file called `aws-ubuntu.pkr.hcl`
	- Add template code to file and edit where necessary.
- **Before you can build the AMI, you need to provide your AWS credentials to Packer as environment environments**
- --------------------------------------------------------
### AWS credentials as environment variables

- Before you can build the AMI, you need to provide your AWS credentials to Packer as environment environments
- 

```
sudo nano .bashrc
  export AWS_ACCESS_KEY_ID=YOUR_ACCESS_KEY
  export AWS_SECRET_ACCESS_KEY=YOUR_SECRET_KEY
source .bashrc
```
**Do not share your keys with anyone, keep them private**
<br> </br>
- -------------------------------------------------
### Initialise, Format and Validate Packer configuration
- Initialise packer
	- Navigate to folder with `aws-ubuntu.pkr.hcl` file
	- Run command `packer init .`
- Format and validate packer
	- Run `packer fmt .`
- Validate packer
	- Run `packer validate .`
	<br> </br>
- -----------------
### Build Packer

- Build the image with this command `packer build aws-ubuntu.pkr.hcl`
<rb> </br>

- --------------
- Additional links

https://www.packer.io/docs/builders/amazon/chroot

https://aaronluna.dev/blog/packer-template-aws-ec2-ubuntu-nginx/

https://chiamakaobitube.medium.com/building-custom-machine-image-using-ansible-packer-and-bash-in-aws-178b93d08136