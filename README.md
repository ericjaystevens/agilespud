Using GO and terraform
======================

Step 1. Create a JS web service using Terraform
-----------------------------------------------

follow along with  https://www.terraform.io/docs/providers/aws/r/lambda_function.html

### proof of completion

```powershell
Invoke-WebRequest  $(terraform output base_url) |select -ExpandProperty content
```
Step 2. Rewrite function in GO
------------------------------

go build -o main main.go
aws s3 cp main.zip s3://samagilespud

### modify terraform



```powershell
teraform apply
Invoke-WebRequest  $(terraform output base_url) |select -ExpandProperty content
```

Step 3. auto build and deploy function with CircleCI
----------------------------------------------------



