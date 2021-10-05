# AKS Labs

##Pre-Requisites

1.	You should have owner access to a resource group (where AKS, virtual network, and other resources will be created). 
2.	GitHub account 

1.	Create Resources

In this lab, you will create a resource group in Azure, virtual network and subnets in Azure, Azure Kubernetes Service and an instance of Azure Container Registry.  

Steps: 
Sign up / Log in to Azure Portal.
http://portal.azure.com 

1.1 Create a resource group 

From the menu on top left, select “Resource Groups”. Click “+Create”.

 

Specify a name for the resource group, and specify a location (for example, West Europe). 

 

Click “Review & Create”, followed by “Create”. The resource group should be created after this step.  

1.2 Create a virtual network and subnets 

Go to the resource group (click on the resource group name) 
Click on +Create

From the menu, select “Networking”
Under “Virtual Networks”, click “Create”. 

 


Provide a name for the resource (For example, vnet-aksdemo). Choose the region as same as the resource group’s region. And Click “Next: IP Addresses>”.

  

In the IP addresses tab, delete the default IPV4 Address Space. 
Add an IPV4 address space: 20.0.0.0/22

click + Add Subnet 

o	Specify a name for the subnet:  snet-aks
o	Specify the IP address range: 20.0.0.0/24

Click “Add” to add the subnet

 
 

Click “Review & Create”, and “Create” to create the virtual network with subnets. 

1.3 Create Azure Container Registry 

Go to the resource group (click on the resource group name) 
Click on +Create
From the menu, select “Containers”
 


In the list of items, under “Container Registry”, click on Create

 

Specify a unique name for the container registry (for example, acrdemo followed by few random numbers).  
Select the region (select the same region of resource group). 
Leave everything else to defaults, and click “Review & Create” followed by “Create”.

 

Enable admin access to the container registry: 
Open the container registry that got created, and in the left menu, select Settings -> Access Keys. 
Toggle “Admin User” to Enabled. 
 

1.4	Create Azure Kubernetes Service instance. 
Go to the resource group (click on the resource group name) 
Click on +Create
From the menu, select “Containers”
Under Kubernetes Service, click “Create”

 


Provide a name for the cluster (for example, aks-demo)
Select the region (same as the resource group’s region)
Leave the defaults for availability zones
Leave the defaults for Kubernetes version. 
Leave the defaults for default node size. 
For scale method, select “Auto Scale”. Select minimum as 1 and maximum as 2. 
 

Click “Next > Node Pools”
In the Node Pools screen, leave the defaults for node pools. 

 

Click “Next > Authentication”
Leave the defaults for authentication. 

 

Click “Next: Networking>”
Change the network plugin from kubenet to Azure CNI. 
Select the VNET you created earlier. 
Select the Subnet you created earlier.
For network policies, select “Calico”. 
 

Select “Next: Integrations>”
Select the container registry you created earlier. 
Leave container monitoring as enabled. 
Select Azure Policy to Enabled. 

 

Click “Review & Create”, and “Create”. 



You can use the [editor on GitHub](https://github.com/francisnazareth/aksworkshop.github.io/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/francisnazareth/aksworkshop.github.io/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
