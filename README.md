# aws_account_cli_access
## Note after your script ran successfully, do this:

`$ source aws_temp_credentials.sh`

# Requirements:
1. Your `iam user` must have been added to the `iam role trsuted policy` to grant the user permissions to assume the role
2. Make sure you have installed `awscli` and have the `keys` to your `iam user`
3. Run `aws configure` and enter the `keys` of your `iam user`
