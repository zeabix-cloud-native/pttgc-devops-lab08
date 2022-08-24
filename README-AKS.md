# Step to create AKS

1. Go to [Azure_Portal](https://azure.microsoft.com/en-us/get-started/azure-portal/) then search kubernetes and select Kubernetes services

<img width="1158" alt="Screen Shot 2565-08-24 at 13 42 46" src="https://user-images.githubusercontent.com/46469458/186349099-679fc9f0-0c51-41f7-baf9-39454eeda184.png">

2. At Kubernetes page click Create and select Create Kubernetes cluster

<img width="1512" alt="Screen Shot 2565-08-24 at 13 46 18" src="https://user-images.githubusercontent.com/46469458/186349841-b4440bd6-3dce-45f9-b23d-a2a12718210b.png">

3. At Create Kubernetes cluster page 

   - resource group select your resource group or create new 

   - cluster preconfiguration select Dev/Test

   - Region select East Asia then click Next: Nood pools
   
<img width="1512" alt="Screen Shot 2565-08-24 at 13 52 55" src="https://user-images.githubusercontent.com/46469458/186351554-150d5cc9-bef6-4684-869b-d796cbc3f008.png">
<img width="1512" alt="Screen Shot 2565-08-24 at 13 53 14" src="https://user-images.githubusercontent.com/46469458/186351565-765bb51e-6a7c-44ca-b7dc-0c6a6fd6788c.png">

4. At Node pools tab click Next: Access

<img width="1512" alt="Screen Shot 2565-08-24 at 14 00 49" src="https://user-images.githubusercontent.com/46469458/186352264-d8ee91f7-dbc2-42fe-8d5c-cff4f6cf5b3a.png">

5. At Access tab click Next: Networking

<img width="1512" alt="Screen Shot 2565-08-24 at 14 04 10" src="https://user-images.githubusercontent.com/46469458/186352934-0018b145-908f-4d1c-8c93-233a84a6ed03.png">

6. At Networking tab click Next: Integrations

<img width="1512" alt="Screen Shot 2565-08-24 at 14 05 23" src="https://user-images.githubusercontent.com/46469458/186353176-7984c494-0276-4906-8d5a-a920b5b81012.png">

7. At Integrations tab 
   - Container registry select your container registry
   - Container monitoring select Enabled
   - Log Analytics workspace click create new then spcecific your workspace name then Create
   - Click Next: Advanced
   
 <img width="1512" alt="Screen Shot 2565-08-24 at 14 10 36" src="https://user-images.githubusercontent.com/46469458/186354335-fd9fbe71-74f4-4aae-a678-c9ea3c006a25.png">

8. At Advanced tab click Next: Tags

<img width="1512" alt="Screen Shot 2565-08-24 at 14 12 56" src="https://user-images.githubusercontent.com/46469458/186354780-9d912a5b-4cda-4c8e-93b8-5f3a6057a693.png">

9. At Tags tab click Next: Review + create

<img width="1512" alt="Screen Shot 2565-08-24 at 14 14 38" src="https://user-images.githubusercontent.com/46469458/186354973-787a83b7-bcc9-4db7-847a-bd5645f67636.png">

10. At Review + create tab you will see overall of your AKS, click Create

<img width="1512" alt="Screen Shot 2565-08-24 at 14 15 51" src="https://user-images.githubusercontent.com/46469458/186355330-40307bee-4f61-459e-9775-3b6fb9044b71.png">
<img width="1512" alt="Screen Shot 2565-08-24 at 14 16 07" src="https://user-images.githubusercontent.com/46469458/186355344-8878f873-df58-4423-a313-4b629479bd9e.png">

11. When deployment success you will see this page

<img width="1512" alt="Screen Shot 2565-08-24 at 15 52 00" src="https://user-images.githubusercontent.com/46469458/186375109-08604579-a675-4476-9777-59eb4af38394.png">

# Step to connect to AKS

1. Go to Kubernetes services and select your cluster then click connect and see step on the right

<img width="1512" alt="Screen Shot 2565-08-24 at 16 29 27" src="https://user-images.githubusercontent.com/46469458/186384815-b094a64c-a0d9-4dcf-9c13-9920216e64fa.png">
