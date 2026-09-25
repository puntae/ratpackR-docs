# GitHub and RStudio Workflow Guide

## Part 1: How to Fork and Clone a Project (Standard Workflow)

1. **Fork the repository on GitHub**
   Navigate to the original project repository on GitHub. Click the **Fork** button in the top right corner of the page. Select your personal account as the destination and click **Create fork**.
2. **Copy your fork's URL**
   Once GitHub redirects you to your newly forked repository, click the green **Code** button. Copy the repository URL (use HTTPS if you use a Personal Access Token, or SSH if you use SSH keys).
3. **Start a Version Control project in RStudio**
   Open RStudio on your laptop. Navigate to **File > New Project...** in the top menu. Select **Version Control**, and then select **Git**.
4. **Clone the repository locally**
   Paste the URL you copied into the **Repository URL** field. The **Project directory name** will automatically populate. Click **Browse** next to the **Create project as subdirectory of** field to choose where you want to save the folder on your laptop.
5. **Initialise the project**
   Click **Create Project**. RStudio will download the files from your GitHub fork and open the new project. You will now see a Git pane in your RStudio environment where you can manage your commits and pushes.

---

## Part 2: How to Keep Your Fork Synchronised

When the main repository is updated, your fork does not synchronise automatically. Use this method to pull the changes down:

1. Go to your forked repository on the GitHub website.
2. Just below the green **Code** button, select the **Sync fork** dropdown.
3. If your fork is behind the original project, click **Update branch**. This updates your fork on GitHub.
4. Open your project in RStudio.
5. In the Git pane, click the blue **Pull** arrow (the down arrow). This downloads the updates from your newly synchronised GitHub fork directly to your laptop.

---

## Part 3: Resolving File Clashes (Merge Conflicts)

If you and the main branch edit the same lines of a file, Git triggers a Merge Conflict.

1. **Identify the clashing files:** In the RStudio Git pane, files with conflicts will display an orange **U** (Unmerged) icon.
2. **Open the file:** Click on the file in RStudio. Git will have added markers to show the clash:
   ```text
   <<<<<<< HEAD
   Your local changes are here
   =======
   The updates from the main branch are here
   >>>>>>> upstream/main
   ```
3. **Edit the code:** Decide which code to keep. Edit the text so the code looks exactly how the final version should work. You must delete all the `<<<<<<<`, `=======`, and `>>>>>>>` markers.
4. **Save the file:** Save your changes in RStudio.
5. **Stage the fixed files:** Go back to the RStudio Git pane and tick the checkbox next to the files you fixed. The orange **U** will turn into a blue **M** (Modified).
6. **Commit to finish:** Click the **Commit** button, leave the default merge message, and click **Commit** again to finalise the process.

---

## Part 4: For Andre Only (Working Directly from the Main Branch)

Because Andre is working directly from the main branch rather than a fork, his workflow is simplified.

### Initial Setup (Clone the Main Branch):
1. Open RStudio and navigate to **File > New Project... > Version Control > Git**.
2. Paste the URL of the original main repository (not a fork).
3. Select a local folder destination and click **Create Project**.

### Synchronising Updates:
To get the latest updates from the main branch, Andre only needs to open his RStudio project, go to the Git pane, and click the blue **Pull** arrow.

### Pushing Changes:
After making edits and committing them, Andre can push his changes directly to the main repository by clicking the green **Push** arrow in the Git pane. (If there are clashes with someone else's recent push, he will resolve them using the steps in Part 3 before pushing).