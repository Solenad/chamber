# Github Account Management

Somehow I get lost between the "Solenad" account and the school account "roedzn"

## **Local use:**

### **Checking the SSH keys:**

```bash
notepad ~/.ssh/config
```
Verify if there are two Github hosts

`Local configs`:
```
# Solenad GitHub account
Host github.com
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519

# [DLSU] roedzn GitHub account
Host github-dlsu
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519_dlsu

```

### **Cloning a repo using a specific account**

`Using Solenad`:
```bash
git clone git@github.com:Solenad/<repository_name>.git
```  
  
`Using roedzn`:
```bash
git clone git@github-dlsu:roedzn/<repository_name>.git
```  
  
### **Switching remote url**

`Using Solenad`:
```bash
git remote set-url git@github.com:Solenad/<repository_name>.git
```  
  
`Using roedzn`:
```bash
git remote set-url git@github-dlsu:roedzn/<repository_name>.git
```  
