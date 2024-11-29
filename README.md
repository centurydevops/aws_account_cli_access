# aws_account_cli_access
## Note after your script ran successfully, do this:

# Requirements:
1. Your `iam user` must have been added to the `iam role trusted policy` to grant the user permissions to assume the role
2. Make sure you have installed `awscli` and have the `keys` to your `iam user`
3. Run `aws configure` and enter the `keys` of your `iam user`

`$ source aws_temp_credentials.sh`

## How can i manage two different github accounts from the same local machine?
Ans:
# sample `~/.ssh/config` file should look like this:

```
# github config for centurydevops
Host github.com-centurydevops
  HostName github.com
  User centurydevops
  IdentityFile ~/.ssh/cent_key
  IdentitiesOnly yes

# etech-technology GitHub account
Host github.com-etech-technology
  HostName github.com
  User etech-technology
  IdentityFile ~/.ssh/id_rsa
  IdentitiesOnly yes
```
# Then run the following commands each time you want to clone a specific repo from a specific github account

1. `git remote set-url origin git@github.com-etech-technology:etech-technology/aws_access.git`
Here you can replace `aws_access` repository with any repository under `etech-technology` github account
2. `git remote set-url origin git@github.com-centurydevops:centurydevops/repo-from-centurydevops.git`
Again here replace `repo-from-centurydevops` with whatever you want from that github account

# Remember that those keys are generated from
`ssh-keygen -t ed25519 -C "email-used-to-create-github-account@gmail.com"`
Enter the path when prompt:
`/Users/your_username/.ssh/id_ed25519_personal` Just hit `enter` on your keyboard till the end

Then `cat ~/.ssh/id_ed25519_personal` and load it to the respective github accounts
