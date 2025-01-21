# Multiple-Github-accounts

Sometimes we need to work with multiple github accounts in one machine. We can’t simply
copy the https url and clone it. We might need an SSH method. For that we have to setup some
configuration in the machine and in Github.

## 1. Generate an SSH-key

## 2. Follow the prompts and decide a name, e.g. github_office.
```
ssh-keygen -t "name for the file" -C "github email"
eg:
ssh-keygen -t "github_office" -C "abc@gmail.com"
```

## 3. Open the pub file using
```
cd .ssh/
cat github_office.pub
```

## 4. Copy the SSH public-key to GitHub from ~/.ssh/.pub and 
## create an SSH key

![image](https://github.com/user-attachments/assets/20f2d563-ca0f-4396-9848-24fc37de1293)

## 5. Create a config file in ~/.ssh with the following contents:
```
Host github-calib-office (name should be similar to git)
HostName github.com
User git
IdentityFile ~/.ssh/github_office
```

## 6. After Adding an SSH key clone the repo using ssh link modify it with the host name.
```
git clone git@github-calib-office:username/repo.git
```
