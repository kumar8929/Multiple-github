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
