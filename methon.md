**学习建议：不会的就问AI。**

使用 SSH 上传文件到 GitHub 的步骤如下：

---

### **1. 生成 SSH 密钥（如果还没有）**
在本地终端运行以下命令生成 SSH 密钥（如果已有，可跳过）：
```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```
- ed25519 是一种算法，专门用于生成 SSH 密钥对，此处也可以使用rsa算法。
- 按回车接受默认保存路径（`~/.ssh/id_ed25519`）。
- 输入密码（可选）。

---

### **2. 将 SSH 密钥添加到 GitHub**
1. 复制公钥内容（`id_ed25519.pub`）：
   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```
2. 登录 GitHub → **Settings** → **SSH and GPG Keys** → **New SSH Key**，粘贴公钥至**Key**，并随便起个名字。

---

### **3. 克隆 GitHub 仓库（SSH 方式）**
在终端中运行：
```bash
git clone git@github.com:username/repository.git
```
- 替换 `username/repository` 为你github上新建的或已存在仓库地址。

---

### **4. 添加文件到本地仓库**
1. 将你想要上传的文件复制到克隆的仓库目录中。
2. 进入仓库目录并添加文件：
   ```bash
   cd repository
   git add .  # 添加所有文件
   ```

---

### **5. 提交更改**
```bash
git commit -m "描述你的更改"
```

---

### **6. 推送到 GitHub**
```bash
git push origin main  # 或分支名（如 master）
```

---

### **常见问题**
1. **权限错误**：确保 SSH 密钥已正确添加到 GitHub。
2. **首次使用 SSH**：运行 `ssh -T git@github.com` 测试连接。
3. **分支名称**：确认你的分支是 `main` 还是 `master`（根据仓库设置）。

---



