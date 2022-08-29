# Step to create Azure Database for MySQL servers
1. Go to [Azure_Portal](https://azure.microsoft.com/en-us/get-started/azure-portal/) then search mysql and select Azure Database for MySQL servers

<img width="1512" alt="Screen Shot 2565-08-29 at 09 29 11" src="https://user-images.githubusercontent.com/46469458/187113552-a6e019e3-3053-4c9f-bcde-7e02a9dba3d0.png">

2. Click Create

<img width="1512" alt="Screen Shot 2565-08-29 at 09 31 49" src="https://user-images.githubusercontent.com/46469458/187115211-a8193ed0-485c-4165-b1b8-f3272ef9ab78.png">

3. Select Single server

<img width="1008" alt="Screen Shot 2565-08-29 at 09 32 49" src="https://user-images.githubusercontent.com/46469458/187115228-6fc546e6-7ed2-4070-bd48-fd79ee976e17.png">

4. At Basic tab

   - Resoure group      : select your resource group
   - Server name        : fill your mysql server name (This is your Endpoint connection)
   - Location           : (Asis Pacific) East Asia
   - Compute + storage  : select Configure server

<img width="1512" alt="Screen Shot 2565-08-29 at 09 33 53" src="https://user-images.githubusercontent.com/46469458/187115297-94149f0f-3b85-4ed8-96c2-ae4febb4961c.png">
<img width="1512" alt="Screen Shot 2565-08-29 at 09 34 50" src="https://user-images.githubusercontent.com/46469458/187115313-0316e82c-67c0-45ec-8123-cbdd00773dfa.png">

5. When click Configure server, configure your mysql server vCore and storage then click OK

<img width="1512" alt="Screen Shot 2565-08-29 at 09 35 53" src="https://user-images.githubusercontent.com/46469458/187115330-c042305a-b9af-4566-bafc-4c7649c4eaf9.png">

6. At Administrator account create your account to connect to your mysql server then click Next: Additional settings

<img width="1512" alt="Screen Shot 2565-08-29 at 09 41 38" src="https://user-images.githubusercontent.com/46469458/187115389-2562f3de-7459-439d-9e52-0b541b40612d.png">

7. At Additional settings tab click Next: Tags

<img width="1512" alt="Screen Shot 2565-08-29 at 09 42 36" src="https://user-images.githubusercontent.com/46469458/187115420-770dd595-4035-4fe6-9e5b-7c6afd4f5076.png">

8. At Tags tab click Next: Review + create

<img width="1512" alt="Screen Shot 2565-08-29 at 09 43 06" src="https://user-images.githubusercontent.com/46469458/187115437-dd9221b6-3f24-48e4-8b24-2d5dd22bfdcc.png">

9. You will see overall of your mysql server, click Create

<img width="1512" alt="Screen Shot 2565-08-29 at 09 43 56" src="https://user-images.githubusercontent.com/46469458/187115444-d56ea4c9-6ff6-45f9-a921-4fb55a2951f9.png">

10. After that when finished you will see this picture

<img width="1512" alt="Screen Shot 2565-08-29 at 09 48 53" src="https://user-images.githubusercontent.com/46469458/187115468-af6e57c1-1b0e-48e1-9ad2-ace5f470c341.png">

# Step to configure Network connection to Azure Database for MySQL servers

1. When Azure Database for MySQL servers has been created click Connection security

   - Firewall rules click + Add 0.0.0.0 - 255.255.255.255 then click continue
   - Enforce SSL connection select DISABLED
   - Click Save

# * This configuration is for the workshop only.  Do not apply to live/production environment.

<img width="1410" alt="Screen Shot 2565-08-29 at 10 43 03" src="https://user-images.githubusercontent.com/46469458/187119588-5c3cbec3-4b57-4043-a211-8136c7133700.png">
