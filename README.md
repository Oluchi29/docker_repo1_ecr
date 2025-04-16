# docker_repo1_ecr
a python project dockerosed and the docker image pushed to eclastic conatiner registry ecr

## STAGES
create a folder infra {This houses the terraform files}
create a dockerfile, jenkinsfile, requirements.txt files

check for changes on each of the files after which you run ur

terraform init
terraform fmt
terraform validate
terraform plan
terraform apply --auto-approve

## ERROR ENCOUNTERED
terraform plan threw an s3 bucket error

## HOW IT WAS RECTIFIED
i deleted what was in the bucket by running
aws s3 rm s3:demo-bucket-2010 --recursive
and re-ran the terraform plan which worked

cd back to the project and push to github

## next stage
put your ip address on the browser and add a :8080 to it to open ur jenkins
when you have successfully logged in go to manage jenkins and install three pluggins
manage jenkins - available plugins - check the below
docker
docker pipeline
amazon ecr

Next new items - description - pipeline - ok
check
github - paste ur github url - select scm - git 
pipelin from scm - paste url - select ur branch if is macter or main
apply - save
 
 ## NOTE BEFORE YOU BUILD CREATE UR IAM ROLE
 how to go about it there are many ways but i choose to do that through aws console
 ## FIRST
 TYPE IAM on the search bar 
 click on roles - create roles - aws service next - give administrative access permissions - 
 next -selest ec2 - create

 do to ec2 check the instnce - on actions - click on security - modify iam - on the drop down select the new role created and click on modify

 back to jenkins go ahead and build


