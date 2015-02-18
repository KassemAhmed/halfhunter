## How to Archive a Project

When a project is over, it gets archived using the archive function within the tool in question, or by putting the folder containing all files into the "Archive" folder in that tool.

There is an archive card included in the client project template on Trello. However, here is the checklist of things that need to get archived, and detailed instructions on how to archive Git repos, which is more complicated than the rest.

- Unshare Dropbox folder, and move it to the **Archive** folder
- Move Google Drive folder to **_Archive** folder
- Export the database, date it, and add it to the repo.
- Archive Git repo (see below)
- Archive Harvest project
- Archive Forecast project
- Archive Slack channel
- Archive InVision project
- Unstar and close Skype room
- Close Trello board
- Remove staging build (site files and database) from dev server

## Archiving Git Repos

We use BitBucket as the archive for all git repositories, with redundant .zip files in Dropbox.

To archive an inactive project's Git repo:

1. If your repo is already in BitBucket, skip to Step 4.

2. If your repo is not already on BitBucket, import the repo to BitBucket using BitBucket's Import function.

  ![Import Repos](/img/screenshots/import_repos_link.png)

3. Make sure the following fields are filled in:

  ![Repo fields](/img/screenshots/import_repos_fields.png)

  And click "Import Repository" submit button.

4. Make sure the site's database is stored in the repo, you have proper documentation, and a detailed README has been written. The goal is to have ZERO [technical debt](/Our_Process/Process_Phases/Development#Technical_Debt) if another developer has to pick this project up again in the future.

5. Navigate to "Downloads" inside of the repo, and download a .zip of the repo to store in Dropbox as a redundant backup. 

  ![Download Repo](/img/screenshots/download_repo.png)

6. Remove 'thephuseteam' from the start of the .zip file, and move the file into our shared Dropbox folder (Phusers > Code Archive > Zipped Git Repos: https://www.dropbox.com/sh/00r9th42krqu1da/AABAaa4EUZkVTlb2ITST8NKna?dl=0) — Make sure you match the naming scheme. The random numbers/letters at the end are the commit# of the last commit on that repo. This is how we can tell if the .zipped version matches what is on BitBucket, and update the folder of Zips accordingly.

7. (If you never used GitHub, skip this one, too!) Double check to make sure the repo made it safely to BitBucket AND Dropbox. Then delete the Repo from Github.\*

  ![Delete Repo](/img/screenshots/delete_repo.png)

\* IMPORTANT NOTE: **DO NOT** delete a repo from Github if the other development team is still using it, or is using a forked copy of the repo without first consulting with the development team using it. In that situation, transferring the repo is probably preferred. Your project manager can facilitate this!

---

The next section talks about how we hire. Read more about [Human Resources&#8594;](/Human_Resources).