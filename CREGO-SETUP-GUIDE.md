# Crego Setup Guide

Follow the steps below to set up your environment for working with Crego repositories and scaffolding new projects.

---

## 1. Create a Workspace Folder
First, create a folder where you will clone or create all repositories related to Crego.  
For example, create a folder called:

```bash
mkdir crego
cd crego
```
---

## 2. Configure Git User for This Folder

Inside the `crego` folder, configure your Git identity so that it uses your **Crego GitHub account** (not your personal one).

```bash
git config user.name "your-crego-username"
git config user.email "your-crego-email@example.com"
```

These settings will apply only inside the `crego` folder and its subfolders.

---

## 3. Create a Personal Access Token (PAT)

You need a **GitHub Classic Personal Access Token (PAT)** with at least the following permission at least:

* `packages:read`

Save this token securely, as it will be used when authenticating with npm.

---

## 4. Configure npm for Crego

Run the following commands inside the `crego` folder to set up npm to work with Crego packages:

```bash
npm config set @crego-in:registry "https://npm.pkg.github.com/" --location=project
```

```bash
npm login --scope=@crego-in --registry=https://npm.pkg.github.com
```

When prompted:

* **Username** → Enter your GitHub account username
* **Password** → Enter the PAT you created earlier
* **Email** → Enter your GitHub email

---

## 5. Scaffold a New Repository

Once npm login is successful, you can create a new repository using the Crego scaffold:

```bash
npm exec crego-init
```

The scaffold will ask:

1. Whether you want a **backend service** or **frontend project** → choose as needed.
2. The **project name** → enter the name of your new repo.

A scaffolded project will then be created.

---

✅ That’s it — your environment is ready!
