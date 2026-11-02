# Push this directory to GitHub

This directory is already initialized as a Git repository on branch `main`. No commit or remote has been created.

1. Create an empty repository on GitHub with your preferred name and visibility. Leave the options to add a README, license, and .gitignore unchecked because this folder already contains project files.
2. Open PowerShell and run:

```powershell
cd C:\Users\liz\Desktop\internship\internship-sensor-analysis
git add .
git commit -m "Add internship sensor software, experimental data, and analysis"
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
git push -u origin main
```

Replace `YOUR_USERNAME` and `YOUR_REPOSITORY` with your GitHub username and repository name. Complete the sign-in prompt if Git asks you to authenticate.

If the commit asks for your identity, configure your preferred commit name and email for this repository, then retry the commit:

```powershell
git config user.name "Your Name"
git config user.email "YOUR_GITHUB_COMMIT_EMAIL"
```

You can use the private commit email shown in your GitHub email settings.

Alternatively, use GitHub Desktop to add this folder as an existing repository, make the initial commit, and publish the repository.

See README.md for the project contents and known analysis limitations. Code and results are preserved from the original work; paths in several analysis scripts still need updating before rerunning them.
