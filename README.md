# wasp-assets
Data files for WaspLib / Simba 1400 (SRL-B).  
These are semi-automated cache dumps.

## Item hashes (Simba 1400 / SRL-B)

`finders/items/data/hash.txt` is **FNV** item hashes for `ItemFinder` Discover / “Load from client”.

They must be produced the same way the client hashes slots:

1. Crop each sprite to **36×23** (drop stack-number rows)
2. Run **CleanItemBackground** (border / shadow cleanup)
3. FNV-hash non-zero pixels

CI does this via `tools/update_items.simba`. Do **not** use CRC32 item hashes for Discover — those were the old Simba 2.0 format and will not match the client.

`id.txt`, `item.txt`, and `hash.txt` must always have the **same line count** (aligned by item id).

## Sections
- [Add assets to wasp](#add-assets-to-wasp)
- [Forking the repository](#forking-the-repository)
- [Enabling GitHub actions](#enabling-github-actions)
- [Merging updates](#merging-updates)

<br/><br/><br/><br/><br/>

## Add assets to wasp
Start the launcher:  
<img width="949" height="678" alt="image" src="https://github.com/user-attachments/assets/3d45a106-2f68-46cf-92db-6fc4554bcfaa" />

Paste this link into the assets link and then click the "Update assets" button:  
```
https://raw.githubusercontent.com/4T0M5PL1TT3R/wasp-assets/refs/heads/main/
```

<img width="925" height="650" alt="image" src="https://github.com/user-attachments/assets/d3876af1-2cbd-43a2-9a42-f022cb1c938c" />

And that's all you need for wasp to work. You should update your assets everytime map or items change in game.

<br/><br/><br/><br/><br/>

## Forking the repository
> [!CAUTION]
> Keep in mind that Jagex might not like you forking this repo and hosting/distributing their assets, follow the rest at your own risk.

First you need a GitHub account.  
Then you need to click the fork button:  
<img width="604" height="202" alt="image" src="https://github.com/user-attachments/assets/c06d0626-07be-421d-97d2-9f7a10d31e7d" />  
On the page that opens keep everything as is and click "Create Fork".

<br/><br/><br/><br/><br/>

## Enabling GitHub actions
This is so the repon semi-automated updater runs every 6h, it will check for updates and if anything changed a Pull Request will be created.  
On your forked repo page go to the settings tab:  
<img width="947" height="232" alt="image" src="https://github.com/user-attachments/assets/5fb530e5-6886-4be5-93bc-a9cac9a8a346" />

<br/><br/>

Then go to the Actions general page:  

<img width="294" height="636" alt="image" src="https://github.com/user-attachments/assets/12ccf080-cab3-488f-8960-848cfcdbfd06" />

<br/><br/>

Ensure the bottom part looks like this with with "Read and Write permissions enabled" and "Allow GitHub Actions to create and approve pull requests" and click save:  
<img width="980" height="367" alt="image" src="https://github.com/user-attachments/assets/b7cc1144-1eb5-4dce-962f-d9648d307c4d" />

And you are done, you should have it checking for updates every 6 hours and creating a Pull Request if there's anything that changed.

<br/><br/><br/><br/><br/>

## Merging updates
When the auto-updater is running, it will run every 6H and if there was anything new it will create a "Pull request" which you need to accept.  
It's not extrmely important to merge them every single time but if there are map changes or new items they will only show on your assets if you merge the pull request.

To do so you can open the "Pull requests" tab on your repository:  
<img width="970" height="575" alt="image" src="https://github.com/user-attachments/assets/cdb46ffe-f2e1-4704-b7fa-8a37e00ed6d9" />

And you should see a list of pull requests:  
<img width="968" height="629" alt="image" src="https://github.com/user-attachments/assets/a70be7e7-1d72-41b4-8e39-60a1048f6c15" />

If you don't merge them frequently you might have multiple and you'll usually want to merge only the latest one (usually the highest number but you should be able to see when they were created too), the other ones you can close them by selecting them and marking them as "closed":  
<img width="973" height="501" alt="image" src="https://github.com/user-attachments/assets/18e6ae7a-dccc-435a-9682-dfcde6af8761" />

Then to merge the latest one, you open it and then you can review it's changes if you want but all you got to do is pressing the green "Merge pull request" button:  
<img width="651" height="205" alt="image" src="https://github.com/user-attachments/assets/1baf50ec-06d2-4dc4-bafa-28c5c9efd441" />

And finally click the green "Confirm merge":  
<img width="615" height="409" alt="image" src="https://github.com/user-attachments/assets/04523924-2005-43cf-bb69-5efb9e7a4da8" />

And that's it! 
