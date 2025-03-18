# 🚀 Manage Multiple GitHub Accounts Like a Pro

Managing multiple GitHub accounts can be challenging, especially when you're constantly switching between personal, work, and open-source accounts. This guide will help you configure your system to handle multiple accounts using SSH keys and Git configurations.

## ✨ **Why Do You Need This?**

- ✅ Seamlessly switch between multiple GitHub accounts
- ✅ Prevent accidental commits to the wrong repository
- ✅ Avoid re-authentication and SSH conflicts
- ✅ Maintain separate configurations for personal and professional work

---

## 🛠️ **What This Setup Includes**

- **SSH Key Management**: Generate and configure SSH keys for different accounts
- **Git Configurations**: Easily manage multiple identities using `.gitconfig`
- **Account Switching**: Automate identity management for each repository
- **Step-by-Step Guide**: Clear instructions for Linux, macOS, and Windows users

---

## 📦 **Prerequisites**

Make sure you have the following installed:  
- [Git](https://git-scm.com/)  
- SSH (OpenSSH)  

---

## 🧑‍💻 **How to Set It Up**

Follow these simple steps:  

1. **Generate SSH Keys for Each Account**  
    ```bash
    ssh-keygen -t ed25519 -C "your-email@example.com"
    ```
    Save each key with a distinct name like `id_ed25519_personal` or `id_ed25519_work`.

2. **Add SSH Keys to GitHub**  
    Copy your SSH key using:
    ```bash
    cat ~/.ssh/id_ed25519_personal.pub
    ```
    Then, add it to your respective GitHub account under **Settings** → **SSH and GPG Keys**.

![image](https://github.com/user-attachments/assets/20f2d563-ca0f-4396-9848-24fc37de1293)

3. **Create a config file in ~/.ssh with the following contents:
to create a config file in mac
```
nano config
```
```
  Host github.com-personal
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519_personal

  Host github.com-work
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519_work
  ```

4. **Configure Git**  
    Create a `.gitconfig` file for each account:
    ```bash
    [user]
      name = Your Name
      email = your-email@example.com
    ```

    Then link it with the correct identity:  
    ```bash
    git config user.name "Your Name"
    git config user.email "your-email@example.com"
    ```

5. **Clone Repositories with Specific Accounts**  
    ```bash
    git clone git@github.com-personal:username/repository.git
    git clone git@github.com-work:username/repository.git
    ```

---

## ⚡ **Additional Tips**

- Verify your active account:  
  ```bash
  git config user.name
  git config user.email
  ```
## 6. After Adding an SSH key clone the repo using ssh link modify it with the host name.
```
git clone git@github-calib-office:username/repo.git
```
