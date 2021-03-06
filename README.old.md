# Dev container for AWS Amplify

This is a codespace template for AWS Amplify in **GitHub Codespace**.

public dockder image for this codespace:

`ghcr.io/mats16/devcontainer-for-aws-amplify:latest` [Github Container Registry](https://github.com/mats16/devcontainer-for-aws-amplify/pkgs/container/devcontainer-for-aws-amplify)

## Configure AWS CLI V2 with AWS SSO

```bash
aws configure sso --profile default
```

The following example generate the SSO profile with `default` as the profile name:

```
$ aws configure sso --profile default

SSO start URL [None]: https://pahud-sso.awsapps.com/start                                                                                                                               
SSO Region [None]: us-east-1                                                                                                                                                            
Attempting to automatically open the SSO authorization page in your default browser.
If the browser does not open or you wish to use a different device to authorize this request, open the following URL:

https://device.sso.us-east-1.amazonaws.com/

Then enter the code:

DJHN-QKRK
The only AWS account available to you is: 123456789012
Using the account ID 123456789012
The only role available to you is: AdministratorAccess
Using the role name "AdministratorAccess"
CLI default client Region [None]: ap-northeast-1                                                                     
CLI default output format [None]:                                                                                    

To use this profile, specify the profile name using --profile, as shown:

aws s3 ls --profile default        
```

## Configure `credential_process` for another profile

The `default` profile is already configured.
If you want to use another profile, Please configure as shown below.

```sh
aws configure set credential_process aws-sso-credential-process --profile <profile_name>
```
