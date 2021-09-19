# [Guide] How to Downgrade apps on AppStore with iTunes 12.6.5 & Charles Proxy (no Jailbreak).

# Table of contents
[I. Notes](#Notes)

[II. Requirements](#requirements)

[III. Let's get into it](#getintoit)




## I. Notes
<a name="Notes"></a>

- The Guide seems complicated, but you only need to do Step 1 to 3 for the first time. And there are 4 steps in total.
- Jailbreak is **NOT** needed. Since the iPA comes directly from iTunes, it's encrypted and can be installed without Sideload. The IPA is 100% legit.
- You can get the old version of any apps on AppStore as long as that version is still **available** on AppStore.


## II. Requirements
<a name="requirements"></a>
- **iTunes 12.6.5** - the latest version of iTunes that supports download apps. Download here (directly from Apple).
- **A Windows machine**: Windows XP/7/10 are supported, not tested on Windows 11 yet.
 
_(Why Windows only? - Apple killed iTunes 12.6.5 on macOS. Even if you manage to get iTunes 12.6.5 on your Mac, the download feature just will does not work.)_
- **Charles Proxy**. I use version 4.2.7 but I don't think it's matter. _(No need to crack Charles Proxy)_
- **An Apple ID for iTunes**. Use a clone ID if you like. Keep in mind that if you switch to another ID, you'll need to re-do the procedure from **Step 3**.
- The `Build Number Version` of the app you want to downgrade. It is a chain of 9 numbers representing the version of the application. You always can get the `Build number Version` most apps on AppStore from [Tool Lantency](https://tools.lancely.tech/apple/app-search). See more info in pictures below:
- Pic 1, 2, 3


## III. Let's get into it
<a name="getintoit"></a>
### 1. Preparing.
- Nothing special about Charles Proxy so I'll focus on iTunes. 
- After you install iTunes succesfully, go to **Edit** => **Preferences** => **Avanced** => Untick **Check for new software updates automatically** to prevent iTunes from asking for update.
- If you get an error about **Library.itl** when opening iTunes: Go to `“C:\Users\Username\My Music\iTunes\”` and delete the existed **Library.itl**
- Login into iTunes with your prepared Apple ID.
- pic 4

### 2. Install Charles Root Certificate
- pic 5678

### 3. Create a Breakpoint








