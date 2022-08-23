# How to create Azure Container Registry (ACR)
1. Login Azure Portal by Microsoft Account 
[Azure_Portal](https://azure.microsoft.com/en-us/get-started/azure-portal/)
2. At search bar type "container registries" then click "Container registries"
<img width="1130" alt="Screen Shot 2565-08-22 at 21 29 36" src="https://user-images.githubusercontent.com/46469458/185946603-c676e3b9-3b33-413a-bbf3-4bce7cfe3de3.png">
3. Click "Create"
<img width="879" alt="Screen Shot 2565-08-22 at 21 09 53" src="https://user-images.githubusercontent.com/46469458/185947009-ce8972a3-38e4-4c5c-84f3-d9a1eca4416a.png">
4. First you must create Resource group click Create new then specific resource group name then click OK
<img width="800" alt="Screen Shot 2565-08-22 at 21 12 00" src="https://user-images.githubusercontent.com/46469458/185947303-378700f9-103f-4fde-9a9f-74d309a80155.png">
5. At Registry name please specific the name of your registry, Location select Southeast Asia, SKU select Basic then click Next: Networking
<img width="783" alt="Screen Shot 2565-08-22 at 21 17 34" src="https://user-images.githubusercontent.com/46469458/185948294-48e85094-5c35-4a58-b3ff-eabcbd9ce38a.png">
6. At Networking tab click Next: Encryption
<img width="782" alt="Screen Shot 2565-08-22 at 21 18 29" src="https://user-images.githubusercontent.com/46469458/185948816-4f9d7ce8-1ef8-468e-bfbb-15d95a2633da.png">
7. At Encrypt tab click Next: Tags
<img width="745" alt="Screen Shot 2565-08-22 at 21 18 59" src="https://user-images.githubusercontent.com/46469458/185948981-920b38be-6730-4ea6-af1f-fe25fa9d9e80.png">
8. At Tags tab click Next: Review + create >
<img width="746" alt="Screen Shot 2565-08-22 at 21 19 18" src="https://user-images.githubusercontent.com/46469458/185949240-5452cda7-4737-4d7b-9b56-69583bd7b42f.png">
9. At Review + create tab you will see summary of your ACR before create 
<img width="711" alt="Screen Shot 2565-08-22 at 21 19 41" src="https://user-images.githubusercontent.com/46469458/185949667-96a3849d-d911-459c-8fce-c9293cc981f0.png">
10. When create completed you can click Go to resource to view your ACR 
<img width="1512" alt="Screen Shot 2565-08-22 at 21 20 02" src="https://user-images.githubusercontent.com/46469458/185950475-6b3c9a1e-24cd-4455-a05e-adf14f01f3bc.png">
11. Create ACR done!!!
<img width="1512" alt="Screen Shot 2565-08-22 at 21 20 39" src="https://user-images.githubusercontent.com/46469458/185950792-f779221a-5a1e-4e44-a7f1-c04a556328d8.png">

# Step to Create credential for docker login 

1. Login to Azure portal 

[Azure_Portal](https://azure.microsoft.com/en-us/get-started/azure-portal/)

2. Select Azure cloud Shell
<img width="1103" alt="Screen Shot 2565-08-23 at 20 35 17" src="https://user-images.githubusercontent.com/46469458/186177823-b282391b-3737-4e11-90ea-e1137378f0ef.png">

3. Select Bash
<img width="1322" alt="Screen Shot 2565-08-23 at 21 00 27" src="https://user-images.githubusercontent.com/46469458/186178298-8ddf771d-7d88-4dd7-9ee3-e5677a03d3c5.png">

Reference : https://docs.microsoft.com/en-us/azure/cloud-shell/overview


4. First command to login to ACR. Please change <resource-group-name> to your resource group name from step 4.
 
 ```console
 groupId=$(az group show \
   --name <resource-group-name> \
   --query id --output tsv)
 ```

5. Second command to login to ACR. create the service principal (Copy JSON result from this step to create AZURE_CREDENTIALS please see detail in step 8.)
 
  ```console
 az ad sp create-for-rbac \
  --scope $groupId \
  --role Contributor \
  --sdk-auth
  ```
 
 <img width="761" alt="Screen Shot 2565-08-23 at 22 35 05" src="https://user-images.githubusercontent.com/46469458/186200948-9cfecd01-e02e-4fa1-a861-d2a8fb24e64c.png">

6. Third command to login to ACR. Please change <registry-name> to your registry name from step 5.

 ```console
 registryId=$(az acr show \
   --name <registry-name> \
   --query id --output tsv)
 ```
 
7. Fourth command to login to ACR. Please change <ClientId> to your client id or app id from step 13. And please keep the result.

  ```console
 az role assignment create \
  --assignee <ClientId> \
  --scope $registryId \
  --role AcrPush
  ```
 
<img width="1512" alt="Screen Shot 2565-08-23 at 20 04 07" src="https://user-images.githubusercontent.com/46469458/186165619-ac871267-2a51-4aed-bc55-60612e7e48c7.png">
 
8. Create Github Repo.

 In the GitHub UI, navigate to your forked repository and select Settings > Secrets > Actions and Select New repository secret to add the following secrets:

 <img width="736" alt="Screen Shot 2565-08-23 at 20 19 26" src="https://user-images.githubusercontent.com/46469458/186168669-1a6ac51f-7e9b-4016-ae4c-b0ead0282b86.png">


Reference : https://docs.microsoft.com/en-us/azure/container-instances/container-instances-github-action
