# Managing Multiple GitHub Accounts

Working with multiple GitHub accounts can be challenging, but it is manageable with the right approach. This guide will walk you through the steps to efficiently handle multiple GitHub accounts on the same machine.

## Table of Contents
1. [Setting Up SSH Keys](#setting-up-ssh-keys)
2. [Configuring SSH](#configuring-ssh)
3. [Setting Up Git Configurations](#setting-up-git-configurations)
4. [Cloning Repositories](#cloning-repositories)
5. [Switching Between Accounts](#switching-between-accounts)

## 1. Setting Up SSH Keys
First, generate SSH keys for each of your GitHub accounts.

**Personal Account:**
```sh
ssh-keygen -t rsa -b 4096 -C "your_personal_email@example.com"
Save the key as ~/.ssh/id_rsa_personal.
Work Account:

sh

ssh-keygen -t rsa -b 4096 -C "your_work_email@example.com"
Save the key as ~/.ssh/id_rsa_work.
Add the generated keys to the SSH agent:

sh

eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa_personal
ssh-add ~/.ssh/id_rsa_work
2. Configuring SSH
Next, create an SSH configuration file to distinguish between the accounts.

Edit (or create) the ~/.ssh/config file:

sh
# Personal GitHub account
Host github.com-personal
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_rsa_personal

# Work GitHub account
Host github.com-work
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_rsa_work
3. Setting Up Git Configurations
Configure Git to use different user information for each repository.

Personal Account:

sh

git config --global user.name "Your Name"
git config --global user.email "your_personal_email@example.com"
For the work account, configure Git per repository:

sh

cd path/to/your/work-repo
git config user.name "Your Name"
git config user.email "your_work_email@example.com"
4. Cloning Repositories
When cloning repositories, use the configured SSH hosts.

Personal Repository:

sh

git clone git@github.com-personal:username/repo.git
Work Repository:

sh

git clone git@github.com-work:work-username/repo.git

5. Switching Between Accounts
Git will automatically use the correct SSH key based on the repository URL. To switch between accounts, simply navigate to the repository's directory.

If you need to push or pull, Git will use the user information configured for that repository.
