# ssh_key_setup
# Self-Service Tool

## 📌 Introduction
Welcome to the **Self-Service Tool** repository! This project aims to provide automation and efficiency improvements through self-service functionalities. This document serves as a comprehensive guide to setting up and using the repository.

## 📂 Project Structure
```
Tool-setup/
│-- src/                 # Source code
│-- docs/                # Documentation
│-- tests/               # Unit tests
│-- .gitignore           # Git ignore file
│-- README.md            # Project documentation
│-- requirements.txt     # Dependencies
│-- config.yaml          # Configuration file
```

## 🚀 Getting Started
### 1️⃣ Prerequisites
Ensure you have the following installed:
- [Python 3.8+](https://www.python.org/downloads/)
- [Git](https://git-scm.com/downloads)

### 2️⃣ Clone the Repository
Using **SSH** (Recommended):
```bash
git clone git@github.com:saranyajeyarama/Self-Service-Tool.git
```
Or using **HTTPS**:
```bash
git clone https://github.com/saranyajeyarama/Self-Service-Tool.git
```

### 3️⃣ Navigate to the Project Directory
```bash
cd Self-Service-Tool
```

### 4️⃣ Set Up a Virtual Environment (Optional but Recommended)
```bash
python -m venv venv
source venv/bin/activate   # For macOS/Linux
venv\Scripts\activate      # For Windows
```

### 5️⃣ Install Dependencies
```bash
pip install -r requirements.txt
```

---

## 🔑 SSH Authentication Setup
To authenticate with GitHub using SSH:

### 1️⃣ Generate SSH Key (If Not Already Done)
```bash
ssh-keygen -t rsa -b 4096 -C "your-email@example.com"
```
Press **Enter** to save the key at the default location.

### 2️⃣ Copy the SSH Key
```bash
type %USERPROFILE%\.ssh\id_rsa.pub   # Windows
cat ~/.ssh/id_rsa.pub                # macOS/Linux
```
Copy the output and add it to GitHub.

### 3️⃣ Add SSH Key to GitHub
- Go to **GitHub > Settings > SSH and GPG Keys**
- Click **New SSH Key**, paste the key, and save it.

### 4️⃣ Test the SSH Connection
```bash
ssh -T git@github.com
```
If successful, you should see:
```
Hi <your-username>! You've successfully authenticated, but GitHub does not provide shell access.
```

---

## 📤 Pushing Changes
After making changes, push them to GitHub:
```bash
git add .
git commit -m "Your commit message"
git push origin main
```

---

## 🤝 Contributing
1. Fork the repository.
2. Create a feature branch (`git checkout -b feature-branch`).
3. Commit changes (`git commit -m "Added a new feature"`).
4. Push to GitHub (`git push origin feature-branch`).
5. Open a Pull Request.

---

## ⚠️ Common Errors & How to Resolve
### 1️⃣ Permission Denied (publickey)
**Error:**
```
Permission denied (publickey).
```
**Solution:**
- Ensure your SSH key is added to GitHub (`~/.ssh/id_rsa.pub`).
- Verify the SSH connection:
  ```bash
  ssh -T git@github.com
  ```
- If the error persists, restart the SSH agent and add the key:
  ```bash
  eval $(ssh-agent -s)
  ssh-add ~/.ssh/id_rsa
  ```

### 2️⃣ Authentication Failed (HTTPS)
**Error:**
```
remote: Support for password authentication was removed on August 13, 2021.
```
**Solution:**
- Use a **Personal Access Token (PAT)** instead of a password.
- Generate a PAT at **GitHub > Settings > Developer Settings > Personal Access Tokens**.
- Use this format to clone:
  ```bash
  git clone https://your-username:<your-token>@github.com/saranyajeyarama/Self-Service-Tool.git
  ```

### 3️⃣ Fatal: Repository Not Found
**Error:**
```
fatal: repository 'https://github.com/saranyajeyarama/Self-Service-Tool.git/' not found
```
**Solution:**
- Verify the repository URL:
  ```bash
  git remote -v
  ```
- Ensure you have access to the repository.
- If using SSH, confirm the correct URL:
  ```bash
  git remote set-url origin git@github.com:saranyajeyarama/Self-Service-Tool.git
  ```

### 4️⃣ Branch Not Found
**Error:**
```
fatal: branch 'main' not found
```
**Solution:**
- Ensure the branch exists:
  ```bash
  git branch -a
  ```
- If missing, check out the correct branch:
  ```bash
  git checkout -b main origin/main
  ```

---

## 📜 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 📞 Contact
For any questions or issues, please raise an **issue** on GitHub or contact the repository owner.

Happy coding! 🚀

