How to create Azure Container Registry (ACR)
1. Login Azure Portal by Microsoft Account 
https://azure.microsoft.com/en-us/get-started/azure-portal/
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
12. First command to login to ACR. Please change <resource-group-name> to your resource group name from step 4.
 groupId=$(az group show \
   --name <resource-group-name> \
   --query id --output tsv)

13. Second command to login to ACR.
 az ad sp create-for-rbac \
  --scope $groupId \
  --role Contributor \
 <img width="586" alt="Screen Shot 2565-08-23 at 19 42 47" src="https://user-images.githubusercontent.com/46469458/186161467-25d265c0-9bb4-43bc-970a-298e67ee2c26.png">
14. Third command to login to ACR. Please change <registry-name> to your registry name from step 5.
 registryId=$(az acr show \
   --name <registry-name> \
   --query id --output tsv)
15. Fourth command to login to ACR. Please change <ClientId> to your client id or app id from step 13. And please keep the result
 az role assignment create \
  --assignee <ClientId> \
  --scope $registryId \
  --role AcrPush
<img width="1512" alt="Screen Shot 2565-08-23 at 20 04 07" src="https://user-images.githubusercontent.com/46469458/186165619-ac871267-2a51-4aed-bc55-60612e7e48c7.png">
16. Create Github Repo 
- In the GitHub UI, navigate to your forked repository and select Settings > Secrets > Actions.
- Select New repository secret to add the following secrets:
AZURE_CREDENTIALS	    The entire JSON output from the service principal creation step
REGISTRY_LOGIN_SERVER	The login server name of your registry (all lowercase). Example: myregistry.azurecr.io
REGISTRY_USERNAME	    The clientId from the JSON output from the service principal creation
REGISTRY_PASSWORD	    The clientSecret from the JSON output from the service principal creation
RESOURCE_GROUP	      The name of the resource group you used to scope the service principal

Reference : https://docs.microsoft.com/en-us/azure/container-instances/container-instances-github-action
