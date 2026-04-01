# MapNet New Zealand
Contents
- [MapNet's Mission](#MapNet's-Mission)
- [This Repository](#This-Repository)
- [Repository Layout](#Repository-Layout)
- [Updating the website](#Updating-the-website)


## MapNet's Mission
To encourage pre-commercial, cross-sector, geme mapping related R&D in a range of organisms valuable to NZ's economy, ecology and culture.

## This Repository
The purpose of this repository is to provide a space for storing and publishing MapNet related information, including hosting the MapNet website https://nzmapnet.github.io/

### Repository Layout
```
📁 nzmapnet.github.io
┣ 📁 _data                             Overarching website information
┣ 📁 _pages                            Pages available to be published to the website
┣ 📁 assets                            Website styling and assets
┃ ┣ 📁 css                             CSS styling
┃ ┗ 📜 ...                             Asset files
┣ 📁 pdfs                              PDFs
┃ ┗ 📜 ...    
┣ 📜 .DS_Store
┣ 📜 Gemfile
┣ 📜 _config.yaml
┣ 📜 google77b8489ab1d401a0.html
┣ 📜 googlef5afe4ad39d25377.html
┗ 📜 robots.txt
```

### Updating the website
Here you will find instructions for how to update the MapNet website for a new year. This is an extensive list but we recommend reading through it completely so you understand the concepts, you may be able to skip some steps.
These instructions are written so that all updates can be made in the Github Web UI.

To make changes to the website without doing a full updat for a new year/meeting, you can follow the same steps and replace the making basic updates step with making your changes.
There are some examples of basic changes you may wish to make further down this doc.

#### Set up
Here we create a branch and PR so that we can keep track of the changes you make before adding them to the main branch.
This is essential as the main branch is protected, so you cannot commit directly to it.
All changes to main must happen via a seperate branch and PR.

1. Create a new branch and name it after the year/meeting/changes you are updating the website for.
    *[https://github.com/NZMapNet/nzmapnet.github.io/branches]*

#### Make basic website updates (for a new year/meeting)
2. Update `_data/authors.yml` to reflect the new year and meeting date.
3. Ensure that when you click "Commit changes..." you are commiting to the branch you have created. (radio-button selection)
      <img width="488" height="530" alt="image" src="https://github.com/user-attachments/assets/ce38fef5-7bcf-4512-8838-a1a1b036cee6" />
4. Restrict the website pages published.
    We recommend as a starting point, keep the pages Information, About, Contact and Conduct.
    As it's likely you don't have all the information yet edit `_data/navigation.yml` by commenting out (adding a `#` at the start of the line) any pages you don't want to be published.
    You can edit this file to publish pages at any point, simply remove the `#` for the page you desire.
    ```
    # The Information page is published
       - title: "Information"
         url: /info/
    
    # The Programme page is NOT published
    #   - title: "Programme"
    #     url: /programme/
    ```
5. Create a new directory under assets. Upload any digital assets you'd like to have displayed on the website to this new directory.
6. Update the home/landing page. Add/update basic details in `_pages/index.md`. We recommend adding in a sentence that other pages and more information will be added and updated closer to the conference date.
7. Update the pages you've chosen to keep published.
8. Update pages you don't currently have published. We recommend a simple "Information will be added closer to the conference date.".
    This is because while these pages can't be navigated to through the website, links to them (like on google), or users directly entering the URL can still access these pages.
    Alternatively you can delete the file for these pages (e.g. `_pages/programme.md`), and they can be recreated in future if needed.

#### Test your changes
**IMPORTANT** Once you are finished testing re-set the branch to `main`.
Github pages only lets one version be live at a time, so while the settings point to any other branch, the main website is unavailable.

8. Navigate to the repository page settings [https://github.com/NZMapNet/nzmapnet.github.io/settings/pages]
9. You will see that the website is configured to deploy from a branch. 
    The branch selected should be `main`. 
    To publish the changes on your branch simply select it from the drop-down and click save.
    You do NOT need to alter the folder from `/(root)`.
10. Navigate to the page deployment action [https://github.com/NZMapNet/nzmapnet.github.io/actions/workflows/pages/pages-build-deployment].
    You should see something like the below, with your branch name in the middle.
    <img width="1282" height="79" alt="image" src="https://github.com/user-attachments/assets/c13e5291-6952-4cd0-b952-a5b40765b73b" />
12. Refresh the page after about 45 seconds and it should update to have a green tick.
    This means that the website is now published based off the branch shown.
    <img width="1158" height="84" alt="image" src="https://github.com/user-attachments/assets/96c382e1-3fa7-4a0c-b852-287cbeb49129" />
14. Visit the website to verify your changes came into effect as expected.
15. You can keep making changes to the code in github. Each time you push a commit to the remote (or commit using the web UI) the webpage will be re-deployed with those changes.
16. **IMPORTANT** Once you are finished your testing session or are happy with your changes return to the page settings and re-set the branch to `main`.

#### Publish your changes
Now that your initial setup changes are tested and ready to go let's publish them.
You can easily come back and repeat this process to make more changes to the published site in future.

17. Open a new [Pull Request](https://github.com/NZMapNet/nzmapnet.github.io/compare) ensuring that the base branch is `main` and the compare branch is the one containing your changes.
18. Your changes will now appear in the Pull Request [tab](https://github.com/NZMapNet/nzmapnet.github.io/pulls) where you can click on "files changed" to see the changes to each file on your branch compared to the main branch.
19. Double check that these are the changes you want published - even better get someone else to check as well.
20. Go to the "Conversation" in the Pull Request and scroll to the bottom.
21. You should see the below.
    If you have merge conflicts, this will be due to multipe people editing the same files at the same time and you will need to resolve these before proceeding.
    <img width="873" height="230" alt="image" src="https://github.com/user-attachments/assets/b1dafb31-9aed-4997-911e-80ccfce90953" />
22. Click the "Squash and Merge" button to merge your changes to the main branch and have them be live on MapNet website.
23. Double check that the branch we are deploying from is `main` in the page settings.
