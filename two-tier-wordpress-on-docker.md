# Welcome to DevOps TechPark repository!

Hi! If you want to learn more about IT and DevOps/SRE tools, Subscribe my  channel  [**DevOps TechPark**](https://www.youtube.com/c/devopstechpark) 

 

## Lean how to run multi container app in  docker and launch 2 tier wordpress app in containers.
### youtube video [**link**](https://www.youtube.com/c/devopstechpark)


 
### Step 1. Create custom docker bridge network for wordpress multi container app

List docker networks
```
docker network list
```
Network create command
```
docker network create wp-net
```
Check network details 

```
docker inspect wp-net
```



### Step 2. Run Mysql container in custom docker network 
```
docker run -d --name db -e MYSQL_ROOT_PASSWORD=Mysql@123 -e MYSQL_DATABASE=wordpress --network wp-net mysql
```

verify mysql container and access container's shell
```
docker ps 
docker exec -it <containerId> bash
```
verify database "wordpress"
```
mysql -pMysql@123
show databases; 
exit
exit
```
###  Step 3. Run Wordpress container in custom network

if you want to provide database details manually from wordpress web UI use following command to run the container in custom network 
```
 docker run -d --name wp --network wp-net -p80:8080 wordpress                                                                                              
``` 
  ###                                 or
use wordpress environment variables to pass database details on runtime
```
 docker run -d --name wp --network wp-net -e WORDPRESS_DB_USER=root -e WORDPRESS_DB_PASSWORD=Mysql@123 -p 80:8080  wordpress
 
```
###  Step 4.  Complete wordpress installation from UI
Open http://localhost:8080 in browser and follow the instruction to complete the wordpress app.


### Cleanup  

```
docker rm -f wp
docker rm -f db
docker network rm  wp-net
```
