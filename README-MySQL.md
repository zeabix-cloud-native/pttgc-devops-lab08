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

# Step to connect to Azure Database for MySQL servers from local computer

1. In this step we require to install MySQL Workbrench on your computer download from [Here](https://dev.mysql.com/downloads/workbench/) and install.

<img width="1512" alt="Screen Shot 2565-08-29 at 13 07 01" src="https://user-images.githubusercontent.com/46469458/187135121-e95af849-f88a-4b4b-994b-5a974784f2cc.png">

2. After that open MySQL Workbrench and click create then configure MySQL Connection 

   - Hostname     :  Copy value from Azure Database for MySQL servers page --> Overview --> Server name
   - Username     :  Copy value from Azure Database for MySQL servers page --> Overview --> Server admin login name

<img width="1512" alt="Screen Shot 2565-08-29 at 13 01 06" src="https://user-images.githubusercontent.com/46469458/187135173-ffa0f7b6-4053-4610-8464-df5f2ca336c5.png">

   - Click test connection and fill your mysql password from step 6. "Step to create Azure Database for MySQL servers " and click OK

<img width="1512" alt="Screen Shot 2565-08-29 at 13 22 15" src="https://user-images.githubusercontent.com/46469458/187136564-07a6771e-7d80-4fb0-b61a-eca32da3db5b.png">

   - This window will appear if a connection is made to Azure Database for MySQL servers, click OK and OK.

<img width="260" alt="Screen Shot 2565-08-29 at 13 24 18" src="https://user-images.githubusercontent.com/46469458/187136866-da847a42-c168-476e-98ff-7c71a83264f1.png">

3. Click on your connection then click on schema tab and right click then select Create Schema... 

<img width="288" alt="Screen Shot 2565-08-29 at 13 30 40" src="https://user-images.githubusercontent.com/46469458/187137431-aa35cef7-b8f1-4c44-8a2c-cbde7282d82a.png">

4. At fill this configuration

   - Schema Name: app
   - Then click apply (1) and apply (2) and close
<img width="1512" alt="Screen Shot 2565-08-29 at 13 36 09" src="https://user-images.githubusercontent.com/46469458/187138835-5f018f20-7683-421a-9b50-1147c1c6e5f6.png">

# * This configuration is for the workshop only.  Do not apply to live/production environment.










