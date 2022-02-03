# migrate existing enterprise domain name to aws route53 and achieve fail over switching between different regions

## operation process 
1. customer should ask the domain name provider to create a record (an NS record) in the domain name management system to authorize a redirect from original entry point to aws Route53 hosted zone. the NS record value should be exactly the same as the record name created in Route53 hosted zone.
2. two alb instances info are as below:
<img width="1175" alt="Screen Shot 2022-02-03 at 4 33 45 PM" src="https://user-images.githubusercontent.com/97269758/152307908-38f3df5b-3866-4b96-8b40-bd222687403f.png">
-------
<img width="1181" alt="Screen Shot 2022-02-03 at 4 34 40 PM" src="https://user-images.githubusercontent.com/97269758/152308008-c67361b9-aaf7-4930-ae32-bc585c6ae86f.png">
3. two health check intances info are as below:
<img width="1207" alt="Screen Shot 2022-02-03 at 4 36 26 PM" src="https://user-images.githubusercontent.com/97269758/152308246-e33229a7-46c7-488e-a97a-7af647c6dd9c.png">
-------
<img width="1205" alt="Screen Shot 2022-02-03 at 4 37 02 PM" src="https://user-images.githubusercontent.com/97269758/152308317-5f78d6ee-2fc7-4195-a324-f44b8513f42c.png">
5. two records under the same Route53 hosted zone need to be created, one is for Region1, the other is for Region2.
<img width="1017" alt="Screen Shot 2022-02-03 at 4 37 50 PM" src="https://user-images.githubusercontent.com/97269758/152308433-086f3ece-e4c3-44ac-8771-8f7f3c5059b3.png">
-------
<img width="1027" alt="Screen Shot 2022-02-03 at 4 40 25 PM" src="https://user-images.githubusercontent.com/97269758/152308816-c7a72ab4-1a34-4e62-a4be-e419c23fe498.png">
6.the records are created as follows:
<img width="1000" alt="Screen Shot 2022-02-03 at 4 41 48 PM" src="https://user-images.githubusercontent.com/97269758/152309021-717cb74e-0994-4497-9355-dad7dc4b72b0.png">
  
