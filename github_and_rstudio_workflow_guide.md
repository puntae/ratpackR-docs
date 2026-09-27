# GitHub and RStudio Workflow Guide

## Part 1: How to Clone the Project and Create a Branch (Standard Workflow)

1. **Copy the repository URL**
   Navigate to the main project repository on GitHub. Click the green **Code** button and copy the repository URL (use HTTPS if you use a Personal Access Token, or SSH if you use SSH keys).
2. **Start a Version Control project in RStudio**
   Open RStudio on your laptop. Navigate to **File > New Project...** in the top menu. Select **Version Control**, and then select **Git**.
3. **Clone the repository locally**
   Paste the URL you copied into the **Repository URL** field. The **Project directory name** will automatically populate. Click **Browse** next to the **Create project as subdirectory of** field to choose where you want to save the folder on your laptop.
4. **Initialise the project**
   Click **Create Project**. RStudio will download the files from the main repository and open the new project. 
5. **Create a new branch**
   In the RStudio Git pane (usually in the top right), click the **New Branch** icon (two purple squares and a white diamond). Give your branch a descriptive name (e.g., `feature-data-cleaning`), ensure "Sync branch with remote" is checked, and click **Create**. You are now working safely in your own isolated branch.

---

## Part 2: How to Keep Your Branch Synchronised

As others update the main branch, your feature branch does not synchronise automatically. Use this method to pull the latest changes into your workspace:

1. In the RStudio Git pane, use the branch dropdown (top right of the pane) to switch from your current feature branch to the `main` branch.
2. Click the blue **Pull** arrow (the down arrow) in the Git pane. This downloads the latest updates from GitHub directly to your laptop.
3. Switch back to your feature branch using the same dropdown menu.
4. Open the **Terminal** tab in RStudio (usually next to the Console) and type `git merge main`, then press Enter. This brings those new updates into your current branch.

---

## Part 3: Resolving File Clashes (Merge Conflicts)

If you and someone else edit the same lines of a file, Git triggers a Merge Conflict during a merge.

1. **Identify the clashing files:** In the RStudio Git pane, files with conflicts will display an orange **U** (Unmerged) icon.
2. **Open the file:** Click on the file in RStudio. Git will have added markers to show the clash:
   ```text
   <<<<<<< HEAD
   Your local changes are here
   =======
   The updates from the main branch are here
   >>>>>>> main
   ```
3. **Edit the code:** Decide which code to keep. Edit the text so the code looks exactly how the final version should work. You must delete all the `<<<<<<<`, `=======`, and `>>>>>>>` markers.
4. **Save the file:** Save your changes in RStudio.
5. **Stage the fixed files:** Go back to the RStudio Git pane and tick the checkbox next to the files you fixed. The orange **U** will turn into a blue **M** (Modified).
6. **Commit to finish:** Click the **Commit** button, leave the default merge message, and click **Commit** again to finalise the process.

---

## Part 4: For Andre Only (Working Directly from the Main Branch)

Because Andre is working directly from the `main` branch rather than creating a separate feature branch, his workflow is simplified.

### Initial Setup:
Andre follows steps 1 through 4 in Part 1 to clone the repository, but **skips Step 5**. He stays on the default `main` branch.

### Synchronising Updates:
To get the latest updates from the main branch, Andre only needs to open his RStudio project, go to the Git pane, and click the blue **Pull** arrow.

### Pushing Changes:
After making edits and committing them, Andre can push his changes directly to the repository by clicking the green **Push** arrow in the Git pane. (If there are clashes with someone else's recent push, he will resolve them using the steps in Part 3 before pushing).