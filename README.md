# ALB-INGRESS-CONTROLLER

1. after creation of cluster go to eks cluster page us and copy oidc url
2. now go to iam and search identity provider and add oidc connect there paste the oidc url there
3. follow below screenshot and click on thumbprint
4. <img width="682" alt="image" src="https://github.com/harsha-209/ALB-INGRESS-CONTROLLER/assets/51083187/3f5f7af5-e6f5-4439-89ac-d0d14028c595">

now create a alb policy and follow below document
https://raw.githubusercontent.com/kubernetes-sigs/aws-load-balancer-controller/v2.6.1/docs/install/iam_policy.json

now go to iam role and create a role using webidentiy and use above oidc url and sts.amazon.com and attach this alb-iam policy 
 <img width="686" alt="image" src="https://github.com/harsha-209/ALB-INGRESS-CONTROLLER/assets/51083187/92a7bb73-6f38-42d2-aebf-5724519dd57a">
now edit the role trust relation ship and add this line in last of policy 
<img width="703" alt="image" src="https://github.com/harsha-209/ALB-INGRESS-CONTROLLER/assets/51083187/8ae49842-ba89-4c46-9d1e-931715ce7822">

now go to official document of alb ingress and edit ingress controller deployment file edit service account add this role arn in alb-ingress controller file and edit cluster name and deploy it. before install certmanage in it
<img width="617" alt="image" src="https://github.com/harsha-209/ALB-INGRESS-CONTROLLER/assets/51083187/316bfdae-855b-437f-9791-10c0482814eb">

