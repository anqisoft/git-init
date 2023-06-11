# git-init

## Description:

This document provides information about using git-init in Windows and the correspondence with git-mentoring.

# Email to git-mentoring:

## Subject:

Using git-init with git bash in Windows creates the master branch, while the default branch for a new repository is main.

## Content:

Hi,

I recently downloaded and installed the latest version of Git on my Windows 10 machine. However, when I used the git-init command, it created the master branch by default. On the GitHub website, when creating a new repository, the default branch is set to main. This creates a discrepancy where I need to use "git push origin master:main" to submit changes instead of simply using "git push origin main" (which doesn't work) or "git push origin master" (which creates an extra branch in the repository).

Therefore, I suggest that when we use the git-init command, it should create the main branch as the default branch for consistency with the repository.

Best regards,
AnQi
June 10, 2023

## Attachment: git-init.pdf

# Response from git-mentoring:

Hi AnQi,

You can configure the default branch that Git creates when running the git init command. This configuration can be set during the Git installation (the installer provides an option), or you can configure it afterwards using the "git config --global init.defaultBranch <branch-name>" command (refer to the documentation: git-scm.com/docs/git-config#Documentation/git-config.txt-initdefaultBranch). By setting the default branch name, Git will use that value as the name for the default branch every time a repository is created.

Regarding the automatic creation of a repository with the same default branch as the remote repository, it is not possible for Git to know which remote repository you are referring to during the git init process. Thus, I believe it is not possible to automatically create a repository with the same default branch. You would need to manually assign a value to the init.defaultBranch configuration variable before running git init.

I hope this information helps. Please feel free to reach out if you have any additional questions or need further clarification.

Thank you!

Regards,
[Hide the name] (he/him)

# Reply to git-mentoring:

Hi [Hide the name],

I want to express my gratitude for your assistance. I have discovered an alternative method for creating a local project and submitting changes, using the "python-help" project as an example. Here are the steps I followed:

1. I visited the https://github.com/new page and created a new repository on github.com. I provided a name (e.g., "python-help"), wrote a description, selected the option "Add a README file," chose a .gitignore template, selected a license, and clicked the "Create Repository" button.
2. On my local machine, I right-clicked on the parent directory and selected "Git Bash Here."
3. In the Git Bash window, I cloned the repository using the command:

```bash
git clone git+ssh://g...@github.com/anqisoft/python-help
```

4. If necessary, I used the "mv" command to change the directory name. For example:

```bash
mv python-help help
```

5. Next, I navigated into the new directory using the "cd" command. For instance: "cd help"
6. To add my name and email to the .git/config file, I executed the following commands:

```bash
Copy code
echo >> .git/config
echo [user] >> .git/config
echo \ \ name = anqisoft >> .git/config
echo \ \ email = anqi...@gmail.com >> .git/config
```

After completing the project using the development tools, I added the files and pushed them with the following commands:

```bash
git add .
git commit -m "initial commit"
git push origin main
```

If you have any further suggestions or questions, please let me know.

Best regards,
AnQi (he/him)
June 11, 2023
